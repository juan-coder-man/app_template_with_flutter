# Activos gráficos para la ficha en Google Play

Referencias de tamaños, formatos y cantidades según la ayuda oficial de Play Console. Los requisitos pueden cambiar; confirma siempre en **Grow users → Store presence → Main store listing → Graphics**.

Documentación oficial: [Add preview assets to showcase your app](https://support.google.com/googleplay/android-developer/answer/9866151).

---

## Mínimo obligatorio (ficha típica solo teléfono)

Para publicar la ficha de tienda necesitas al menos **icono de la app**, **gráfico destacado** y **dos capturas** (reglas generales de capturas abajo). Hasta **8 capturas** por tipo de dispositivo.

| Activo              | Dimensiones         | Formato                                  | Notas                                                                                                                                           |
| ------------------- | ------------------- | ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Icono (Play Store)  | **512 × 512** px    | PNG **32 bits** (con alpha)              | Máx. **1024 KB**. Debe cumplir las [especificaciones de icono](https://developer.android.com/google-play/resources/icon-design-specifications). |
| Gráfico destacado   | **1024 × 500** px   | JPEG o PNG **24 bits** (sin alpha)       | Se usa como portada; si hay vídeo de vista previa, actúa de fondo del reproductor.                                                              |
| Capturas (teléfono) | Ver tabla siguiente | JPEG o PNG (según políticas de capturas) | Mínimo **2** capturas en conjunto para la ficha; máx. **8** por tipo de dispositivo.                                                            |

### Reglas generales de capturas de pantalla (teléfono y resto de tipos salvo donde se indique lo contrario)

| Requisito       | Valor                                                                 |
| --------------- | --------------------------------------------------------------------- |
| Cantidad mínima | **2** capturas (en conjunto entre los tipos de dispositivo que uses). |
| Lado máximo     | **3840 px** en la dimensión mayor.                                    |
| Proporción      | La dimensión **mayor no puede ser más del doble** que la **menor**.   |
| Contenido       | Debe reflejar la experiencia real dentro de la app o el juego.        |

---

## Muy recomendado (promoción y superficies de recomendación)

Cumplir lo siguiente **no** es obligatorio para tener ficha publicada, pero Google lo exige para ser elegible en formatos que usan capturas en recomendaciones y promoción.

| Contexto   | Capturas       | Orientación y mínimos sugeridos                                                                                                                          |
| ---------- | -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Apps**   | Al menos **4** | Lado corto mín. **1080 px**. **16:9** horizontal mín. **1920 × 1080** px, o **9:16** vertical mín. **1080 × 1920** px.                                   |
| **Juegos** | Al menos **3** | Tres capturas **16:9** horizontal (mín. **1920 × 1080** px) **o** tres **9:16** verticales (mín. **1080 × 1920** px), mostrando la experiencia de juego. |

| Activo opcional           | Descripción                                                                                                                                                                                                                                                                  |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Vídeo de vista previa** | URL de un vídeo en **YouTube** (no lista ni canal). No obligatorio en general; **muy recomendado** para juegos; en algunas zonas de Play los juegos pueden necesitarlo para aparecer. Anuncios del vídeo desactivados; sin restricción de edad que impida mostrarlo en Play. |

---

## Obligatorio solo si publicas en estas plataformas

### Tablet y Chromebook (pantallas grandes)

Si añades capturas para **Chromebook** o **tablet**:

| Requisito           | Valor                                       |
| ------------------- | ------------------------------------------- |
| Cantidad mínima     | **4** capturas                              |
| Tamaño (lado)       | Entre **1080** y **7680** px                |
| Relación de aspecto | **16:9** (horizontal) o **9:16** (vertical) |

### Wear OS

Si distribuyes en **Wear OS**:

| Requisito     | Valor                                                                                                                                                                                    |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Capturas      | Al menos **1** que refleje la versión actual en Wear OS                                                                                                                                  |
| Relación      | **1:1**                                                                                                                                                                                  |
| Tamaño mínimo | **384 × 384** px                                                                                                                                                                         |
| Restricciones | Sin marcos de dispositivo; solo interfaz de la app; sin fondos ni texto gráfico añadido que no sea parte de la UI; sin fondos transparentes ni enmascarado donde la política lo prohíba. |

### Android TV

Si distribuyes app para **Android TV**:

| Activo      | Dimensiones                  | Formato                            | Notas                                                                     |
| ----------- | ---------------------------- | ---------------------------------- | ------------------------------------------------------------------------- |
| Capturas TV | Según sección TV en la ayuda | —                                  | Al menos **1** captura de TV antes de publicar en ese canal.              |
| Banner TV   | **1280 × 720** px            | JPEG o PNG **24 bits** (sin alpha) | Obligatorio para apps habilitadas para Android TV; solo se muestra en TV. |

### Android Automotive OS

Las reglas dependen de la [categoría de la app](https://developer.android.com/training/cars#supported-app-categories): en categorías “parked” las capturas pueden ser opcionales; fuera de ellas suelen ser obligatorias.

Si **incluyes** capturas específicas de Automotive OS, la ayuda exige al menos **2 verticales** (**800 × 1280** px) y **2 horizontales** (**1024 × 768** px).

### Android XR

| Requisito           | Valor                                                     |
| ------------------- | --------------------------------------------------------- |
| Cantidad            | Entre **4** y **8** capturas                              |
| Relación de aspecto | **8:5**                                                   |
| Formato             | PNG o JPEG, hasta **8 MB** por imagen                     |
| Resolución          | Recomendado **3840 × 2400** px; mínimo **1920 × 1200** px |

---

## Resumen rápido: opcional vs obligatorio

| Situación                                           | Qué subir como mínimo gráfico                                                    |
| --------------------------------------------------- | -------------------------------------------------------------------------------- |
| Solo teléfono                                       | Icono 512², gráfico 1024×500, **2+** capturas teléfono (hasta 8).                |
| Quieres mejor visibilidad en recomendaciones (apps) | **4** capturas con mínimos 1080 px / 16:9 o 9:16 indicados arriba.               |
| Quieres mejor visibilidad (juegos)                  | **3** capturas 16:9 o **3** en 9:16 con mínimos indicados.                       |
| Tablets / Chromebook                                | Si añades bloque de capturas grandes: **4** capturas, 1080–7680 px, 16:9 o 9:16. |
| Wear OS / TV / Automotive / XR                      | Aplica la tabla condicional correspondiente.                                     |

---

## Buenas prácticas breves

- Añade **texto alternativo (alt)** a cada imagen (Google sugiere hasta **140 caracteres**, sin empezar por “foto de…” o “imagen de…”).
- Las capturas deben mostrar la **experiencia real** de la app; evita reclamaciones de ranking, precio o descargas, y CTAs tipo “instala ya” según la [política de metadatos](https://support.google.com/googleplay/android-developer/answer/9898842).
- **Gráfico destacado:** evita duplicar el mismo protagonismo visual del icono; ten en cuenta zonas de recorte que la interfaz de Play puede aplicar.
