# Firma Android y build de entrega (AAB/APK)

Este documento describe el flujo recomendado para configurar firma de release en Android, generar el archivo de subida a Google Play (`.aab`) y dejar documentado el renombre de empresa/app en todas las plataformas.

**Application ID (placeholder):** `com.tu_empresa.tu_app`  
**Keystore en disco:** `credentials/upload-keystore.jks`  
**Guía general del repo:** [README.md](../../README.md)

---

## Paso 1 — Crear y mantener `android/key.properties`

**Ruta del archivo:** `android/key.properties` (al mismo nivel que `android/app/`).

Gradle carga este archivo desde el `rootProject` de Android.

Contenido base recomendado:

```properties
storePassword=tu_store_password
keyPassword=tu_key_password
keyAlias=upload
storeFile=../../credentials/upload-keystore.jks
```

- `storeFile` es relativa al módulo `android/app/` y apunta a `credentials/upload-keystore.jks` en la raíz del proyecto.
- Sustituye los placeholders por valores reales y no publiques secretos fuera de los archivos de configuración esperados.

---

## Paso 2 — Configurar firma release en `android/app/build.gradle.kts`

**Ruta del archivo:** `android/app/build.gradle.kts`.

Este template inicia con firma de debug para `release`. Debes añadir la carga de `key.properties`, evaluar `releaseSigningReady` y aplicar la `signingConfig` de release solo cuando esté lista.

Bloque recomendado:

```kotlin
import java.util.Properties

plugins {
    id("com.android.application")
    id("kotlin-android")
    id("dev.flutter.flutter-gradle-plugin")
}

// INI AGREGADO PARA FIRMA
val keystorePropertiesFile = rootProject.file("key.properties")
val keystoreProperties = Properties()
if (keystorePropertiesFile.exists()) {
    keystorePropertiesFile.inputStream().use { keystoreProperties.load(it) }
}

val storePath = keystoreProperties.getProperty("storeFile")
val releaseStoreFile = storePath?.let { file(it) }
val releaseSigningReady =
    releaseStoreFile != null &&
        releaseStoreFile.exists() &&
        !keystoreProperties.getProperty("keyAlias").isNullOrBlank() &&
        !keystoreProperties.getProperty("keyPassword").isNullOrBlank() &&
        !keystoreProperties.getProperty("storePassword").isNullOrBlank()
// FIN AGREGADO PARA FIRMA

android {
    namespace = "com.tu_empresa.tu_app"
    compileSdk = flutter.compileSdkVersion
    ndkVersion = flutter.ndkVersion

    compileOptions {
        sourceCompatibility = JavaVersion.VERSION_17
        targetCompatibility = JavaVersion.VERSION_17
    }

    kotlinOptions {
        jvmTarget = JavaVersion.VERSION_17.toString()
    }

    defaultConfig {
        applicationId = "com.tu_empresa.tu_app"
        minSdk = flutter.minSdkVersion
        targetSdk = flutter.targetSdkVersion
        versionCode = flutter.versionCode
        versionName = flutter.versionName
    }

    // INI AGREGADO PARA FIRMA
    signingConfigs {
        if (releaseSigningReady) {
            create("release") {
                keyAlias = keystoreProperties.getProperty("keyAlias")
                keyPassword = keystoreProperties.getProperty("keyPassword")
                storeFile = releaseStoreFile
                storePassword = keystoreProperties.getProperty("storePassword")
            }
        }
    }
    // FIN AGREGADO PARA FIRMA

    // INI MODIFICAO PARA FIRMA
    buildTypes {
        release {
            signingConfig =
                if (releaseSigningReady) {
                    signingConfigs.getByName("release")
                } else {
                    signingConfigs.getByName("debug")
                }
        }
    }
    // FIN MODIFICADO PARA FIRMA
}

flutter {
    source = "../.."
}
```

En `android { ... }`:

- Define `namespace` y `applicationId` con tu valor final (ejemplo: `com.tu_empresa.tu_app`).
- Crea `signingConfigs { create("release") { ... } }` si `releaseSigningReady` es verdadero.
- En `buildTypes.release`, usa:
  - `signingConfigs.getByName("release")` cuando hay firma lista.
  - fallback temporal a `signingConfigs.getByName("debug")` cuando no está lista.

---

## Paso 3 — Crear el keystore en `credentials/`

Desde la raíz del proyecto:

```bash
mkdir -p credentials

keytool -genkeypair -v \
  -keystore credentials/upload-keystore.jks \
  -alias upload \
  -keyalg RSA \
  -keysize 2048 \
  -validity 10000 \
  -storetype JKS
```

`keytool` pedirá:

1. Contraseña del keystore (`storePassword`).
2. Contraseña de la clave (`keyPassword`) si aplica.
3. Datos DN del certificado (CN, OU, O, L, ST, C).

Checklist DN (plantilla):

| Campo                    | Valor |
| ------------------------ | ----- |
| CN (nombre y apellidos)  |       |
| OU (unidad organizativa) |       |
| O (organización)         |       |
| L (ciudad)               |       |
| ST (provincia/estado)    |       |
| C (país, 2 letras)       |       |

`keyAlias` debe coincidir con el valor definido en `android/key.properties` (por defecto, `upload`).

---

## Paso 4 — Renombrar empresa/app en todas las plataformas

Antes de publicar, reemplaza los valores de ejemplo (`com.example`, `app_template_with_flutter`) por los de tu producto.

### 4.1 Android

- **Identificador reverse-domain en minúsculas** (`com.tu_empresa.tu_app`) en:
  - `android/app/build.gradle.kts` (`namespace`, `applicationId`)
  - `android/app/src/main/kotlin/com/example/app_template_with_flutter/MainActivity.kt` (ruta de paquete y `package`)
- **Nombre visible de app** en:
  - `android/app/src/main/AndroidManifest.xml` (`android:label`)

### 4.2 iOS

- **Bundle ID reverse-domain** en:
  - `ios/Runner.xcodeproj/project.pbxproj` (`PRODUCT_BUNDLE_IDENTIFIER`)
- **Nombre visible** en:
  - `ios/Runner/Info.plist` (`CFBundleDisplayName`)
  - `ios/Runner/Info.plist` (`CFBundleName`, si necesitas nombre técnico distinto)

### 4.3 macOS

- **Bundle ID y nombre de producto** en:
  - `macos/Runner/Configs/AppInfo.xcconfig` (`PRODUCT_BUNDLE_IDENTIFIER`, `PRODUCT_NAME`, `PRODUCT_COPYRIGHT`)
- **Validar targets/configs** en:
  - `macos/Runner.xcodeproj/project.pbxproj`

### 4.4 Web

- **Nombre visible y metadatos públicos** en:
  - `web/manifest.json` (`name`, `short_name`, `description`)
  - `web/index.html` (`<title>`, `apple-mobile-web-app-title`, `meta description`)

### 4.5 Windows

- **Nombre de proyecto/binario** en:
  - `windows/CMakeLists.txt` (`project`, `BINARY_NAME`)
- **Empresa, producto y metadatos del ejecutable** en:
  - `windows/runner/Runner.rc` (`CompanyName`, `FileDescription`, `ProductName`, `OriginalFilename`, `LegalCopyright`)

### 4.6 Linux

- **ID de aplicación reverse-domain y binario** en:
  - `linux/CMakeLists.txt` (`APPLICATION_ID`, `BINARY_NAME`)
- **Título de ventana** en:
  - `linux/runner/my_application.cc` (`gtk_header_bar_set_title`, `gtk_window_set_title`)

### 4.7 Nombre base Flutter

- `pubspec.yaml` (`name`) en `snake_case`.
- Mantén coherencia entre:
  - nombre técnico (`snake_case`)
  - nombre visible (Title Case para tiendas/sistema)
  - identificadores de paquete (`reverse-domain` en minúsculas)

---

## Después — Generar artefactos firmados

Desde la raíz del proyecto:

```bash
flutter build appbundle
```

Salida esperada para Play Store:

`build/app/outputs/bundle/release/app-release.aab`

APK opcional:

```bash
flutter build apk --release
```

Salida esperada:

`build/app/outputs/flutter-apk/app-release.apk`

Si falta el `.jks` o `android/key.properties` está incompleto, el release puede terminar con firma debug. Verifica siempre antes de publicar.

---

## Referencias rápidas

| Elemento                 | Ubicación                         |
| ------------------------ | --------------------------------- |
| Propiedades de firma     | `android/key.properties`          |
| Configuración Gradle app | `android/app/build.gradle.kts`    |
| Keystore (no versionar)  | `credentials/upload-keystore.jks` |
| Índice de documentación  | [README.md](README.md)            |
