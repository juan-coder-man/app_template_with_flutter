# Guía para publicar en App Store (iOS)

Esta carpeta agrupa referencias para publicar la aplicación Flutter en la App Store. Es una **guía operativa**; sustituye o amplía según tu caso y consulta siempre la [documentación oficial de Apple](https://developer.apple.com/app-store/submissions/) y la de Flutter sobre [compilación y publicación en iOS](https://docs.flutter.dev/deployment/ios).

## 1. Requisitos previos

- Cuenta activa en el [Apple Developer Program](https://developer.apple.com/programs/) (cuota anual).
- Mac con **Xcode** instalado y actualizado (desde App Store o developer.apple.com).
- Flutter instalado y `flutter doctor` sin bloqueos críticos para iOS. (--- REVISAR PERIODICAMENTE ---)
- Dispositivo físico iOS opcional para pruebas previas a envío.

## 2. App Store Connect

1. Entra en [App Store Connect](https://appstoreconnect.apple.com/) con tu Apple ID de desarrollador.
2. Completa **acuerdos, impuestos y bancarios** si te lo solicita la consola (necesario para apps de pago o con compras).
3. En [**Mis apps**](https://appstoreconnect.apple.com/apps), pulsa **+** → **New App** / **Nueva app**. Rellena el formulario de nueva app y el de **Register a new bundle ID in Certificates, Identifiers & Profiles** (o entra en [Certificates, Identifiers & Profiles](https://developer.apple.com/account/resources/identifiers/list), para que el paquete de la app aparezca como opción seleccionable, el identificador ya debe estar definido en la app es el que aparece al revisar la sección de **Signing & Capabilities** desde Xcode, mas adelante en este documento se explica como llegar allí <span style="color:#16a34a">**(--- PARA TODAS LAS APPS ---)**</span>

## 3. Configura los certificados y perfiles en Xcode

1. Abre Xcode → **Settings** → **Accounts**.
2. Agrega tu Apple ID asociado a la organización.
3. Selecciona tu **Team** (verás el nombre de tu organización, no tu nombre personal).
4. Haz clic en **Manage Certificates** → **+** y crea un certificado de tipo **Apple Distribution**.

## 4. Registro de Dispositivo (Necesario para compilar)

Apple requiere que haya al menos un dispositivo físico registrado en tu cuenta para generar los perfiles de aprovisionamiento, incluso si solo vas a generar el archivo para la tienda. Si no tienes un iPhone a mano, puedes registrar tu **Mac (si es Apple Silicon M1/M2/M3,etc)**.

1. **Obtén el Provisioning UDID de tu Mac:**
   - Haz clic en el menú **Apple ()** → Mantén presionada la tecla **Option (Alt)** → **Información del Sistema...**
   - En la sección **Hardware**, busca el campo llamado **Provisioning UDID**.
   - Copia ese código (ejemplo: `00008101-001A24422102001E`).

2. **Regístralo en el Portal de Desarrolladores:**
   - Ve a [Certificates, Identifiers & Profiles > Devices](https://developer.apple.com/account/resources/devices/list).
   - Haz clic en el botón **"+"**.
   - En **Platform**, selecciona **macOS**.
   - En **Device Name**, asigna un nombre (ej: "Mac de Juan").
   - En **UUID**, pega el código que copiaste anteriormente y finaliza el registro.

## 5. Configura la firma del proyecto iOS (Runner) en Xcode

1. Abre el proyecto iOS correcto:
   - Desde Xcode: **File** → **Open...** → selecciona `ios/Runner.xcworkspace`.
2. En el panel izquierdo, haz clic en el proyecto **Runner** (icono azul).
3. En el área central, bajo **TARGETS**, selecciona **Runner** (no “RunnerTests”).
4. Ve a la pestaña **Signing & Capabilities**.
5. Configura los campos:
   - Activa **Automatically manage signing**.
   - En **Team**, selecciona tu Team (el mismo que usas en App Store Connect).
   - En **Bundle Identifier**, escribe o verifica el identificador (debe coincidir con el **Bundle ID** de la app creada en App Store Connect).
     <span style="color:#16a34a">**(--- PARA TODAS LAS APPS ---)**</span>

## 6. Generar el Build de Producción

Desde la terminal en la raíz de tu proyecto Flutter, ejecuta:

```bash
flutter build ipa
```

<span style="color:#16a34a">**(--- PARA TODAS LAS APPS ---)**</span>

- **Gestión de Permisos de macOS (Keychain):**
  - Durante la compilación, macOS solicitará permiso para acceder al Llavero (Keychain) para usar el certificado de firma.
  - Aparecerá una ventana pidiendo la contraseña de tu Mac.
  - **IMPORTANTE:** Introduce tu contraseña de inicio de sesión y selecciona **"Always Allow"** (Permitir siempre) para evitar que la ventana aparezca repetidamente por cada componente firmado.

## 7. Subir el build a App Store Connect

El flujo recomendado es generar un **Archive** desde Xcode y distribuirlo desde el **Organizer**.

1. **Abre el proyecto iOS correcto:**
   - Desde Xcode: **File** → **Open...** → selecciona `ios/Runner.xcworkspace`.
   - No abras `ios/Runner.xcodeproj`, porque en Flutter el `.xcworkspace` incluye las dependencias de CocoaPods.

2. **Selecciona el destino de compilación:**
   - En la barra superior de Xcode, selecciona el scheme **Runner**.
   - Como destino, selecciona **Any iOS Device (arm64)**, **Generic iOS Device** o un iPhone físico conectado.
   - No selecciones un simulador, porque Xcode no permite crear un archive para distribución desde simulador.

3. **Crea el archive:**
   - En el menú superior, ve a **Product** → **Archive**.
   - Espera a que Xcode compile y firme la app.
   - Si aparecen errores de firma, revisa nuevamente el paso 5 (**Signing & Capabilities**) y vuelve a intentar.

4. **Distribuye el archive:**
   - Cuando termine la compilación, Xcode abrirá **Organizer** automáticamente.
   - Si no se abre, ve a **Window** → **Organizer** → **Archives**.
   - Selecciona el archive más reciente de **Runner**.
   - Pulsa **Distribute App**.
   - Selecciona **App Store Connect**.
   - Selecciona **Upload**.
   - Continúa con las opciones por defecto, revisa la validación final y pulsa **Upload**.

5. **Verifica en App Store Connect:**
   - Entra en [App Store Connect → Mis apps](https://appstoreconnect.apple.com/apps) → selecciona tu app → pestaña **TestFlight** o **Distribución**.
   - El build aparecerá inicialmente como **Procesando** (puede tardar de unos minutos hasta una hora).
   - Cuando termine de procesarse, quedará disponible para asignarlo a una versión y enviarlo a revisión.

<span style="color:#16a34a">**(--- PARA TODAS LAS APPS ---)**</span>

## Resumen: pasos a revisar en cada nueva app

Antes de publicar una **nueva app**, repasa siempre estos pasos (los marcados con <span style="color:#16a34a">**(--- PARA TODAS LAS APPS ---)**</span>):

| Paso | Sección                        | Qué revisar / actualizar                                                                |
| ---- | ------------------------------ | --------------------------------------------------------------------------------------- |
| 2    | App Store Connect              | Crear el registro de la app y el **Bundle ID** en Certificates, Identifiers & Profiles. |
| 5    | Signing & Capabilities (Xcode) | **Team** correcto y **Bundle Identifier** coincidente con el de App Store Connect.      |
| 6    | Build de producción            | Ejecutar `flutter build ipa` y aceptar permisos del Llavero.                            |
| 7    | Subir a App Store Connect      | `Product > Archive` en Xcode → `Organizer` → `Distribute App` → `Upload`.               |

> Adicionalmente, revisa el paso 1 cada cierto tiempo (`flutter doctor`, versión de Xcode y certificados vigentes).
