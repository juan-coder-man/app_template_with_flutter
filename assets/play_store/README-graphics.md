# Activos gráficos para la ficha en Google Play

Referencias según los textos que muestra Play Console en **Grow users → Store presence → Main store listing → Graphics**. Revisa antes de subir materiales las [directrices de contenido](https://support.google.com/googleplay/android-developer/answer/9900383) del programa. Si añades traducciones de la ficha sin gráficos localizados, Play usará los del idioma predeterminado.

Documentación oficial: [Add preview assets to showcase your app](https://support.google.com/googleplay/android-developer/answer/9866151).

---

## Icono de la aplicación _(obligatorio)_

| Requisito    | Valor                                                                                                                                                                                                                                                                             |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Dimensiones  | **512 × 512** px                                                                                                                                                                                                                                                                  |
| Formato      | **PNG** o **JPEG**                                                                                                                                                                                                                                                                |
| Tamaño       | Como máximo **1 MB** (1024 KB)                                                                                                                                                                                                                                                    |
| Cumplimiento | [Especificaciones de diseño del icono](https://developer.android.com/google-play/resources/icon-design-specifications) y [política de metadatos](https://support.google.com/googleplay/android-developer/answer/9898842). La consola permite previsualización del recurso subido. |

---

## Gráfico de funciones / gráfico destacado _(obligatorio)_

En la interfaz española aparece como **«Gráfico de funciones»**; equivale al _feature graphic_ de la ayuda en inglés.

| Requisito    | Valor                                                                                            |
| ------------ | ------------------------------------------------------------------------------------------------ |
| Dimensiones  | **1024 × 500** px                                                                                |
| Formato      | **PNG** o **JPEG**                                                                               |
| Tamaño       | Como máximo **15 MB**                                                                            |
| Uso habitual | Cabecera de la ficha; si hay vídeo de vista previa, suele utilizarse como fondo del reproductor. |

---

## Vídeo

Campo habitual de la misma página de **Graphics**.

| Requisito     | Condición                                                                                          |
| ------------- | -------------------------------------------------------------------------------------------------- |
| URL           | Vídeo de **YouTube** (pública o **solo con enlace**/no listada según permite la política vigente). |
| Anuncios      | **Desactivados** en el vídeo.                                                                      |
| Restricciones | **Sin** restricción de edad que impida mostrarlo en Play tal como indica la consola.               |

video:

```
https://www.youtube.com/watch?v=
```

---

## Capturas por tipo de dispositivo

Los límites son los que muestra cada bloque en **Graphics**. Donde aplique **16:9 / 9:16** son **horizontal** u **vertical** respectivamente.

### Teléfono _(obligatorio)_

| Requisito            | Valor                                 |
| -------------------- | ------------------------------------- |
| Cantidad             | Entre **2** y **8** capturas          |
| Formato              | **PNG** o **JPEG**                    |
| Tamaño por archivo   | Como máximo **8 MB**                  |
| Relación de aspecto  | **16:9** o **9:16**                   |
| Lados (ancho / alto) | Cada lado entre **320** y **3840** px |

### Tablet 7" _(obligatorio)_

| Requisito           | Valor                                          |
| ------------------- | ---------------------------------------------- |
| Cantidad            | Hasta **8** capturas (según bloque en consola) |
| Formato             | **PNG** o **JPEG**                             |
| Tamaño por archivo  | Como máximo **8 MB**                           |
| Relación de aspecto | **16:9** o **9:16**                            |
| Lados               | Cada lado entre **320** y **3840** px          |

### Tablet 10" _(obligatorio)_

| Requisito           | Valor                                  |
| ------------------- | -------------------------------------- |
| Cantidad            | Hasta **8** capturas                   |
| Formato             | **PNG** o **JPEG**                     |
| Tamaño por archivo  | Como máximo **8 MB**                   |
| Relación de aspecto | **16:9** o **9:16**                    |
| Lados               | Cada lado entre **1080** y **7680** px |

### Chromebook

| Requisito           | Valor                                  |
| ------------------- | -------------------------------------- |
| Cantidad            | Entre **4** y **8** capturas           |
| Formato             | **PNG** o **JPEG**                     |
| Tamaño por archivo  | Como máximo **8 MB**                   |
| Relación de aspecto | **16:9** o **9:16**                    |
| Lados               | Cada lado entre **1080** y **7680** px |

### Android XR

| Requisito           | Valor                                 |
| ------------------- | ------------------------------------- |
| Cantidad            | Entre **4** y **8**                   |
| Formato             | **PNG** o **JPEG**                    |
| Tamaño por archivo  | Como máximo **15 MB**                 |
| Relación de aspecto | **16:9** o **9:16**                   |
| Lados               | Cada lado entre **720** y **7680** px |

**Vídeo de XR espacial**: URL de **YouTube**; formato inmersivo **360°, 180° o 3D**; público o no listado; **sin anuncios** y **sin** restricción de edad que impida la reproducción en Play según indicación en consola.

```
https://www.youtube.com/watch?v=
```

**Vídeo de XR no espacial**: URL de **YouTube**; público o no listado; **sin anuncios** y **sin** restricción de edad según consola.

```
https://www.youtube.com/watch?v=
```

---

## Muy recomendado (promoción y superficies de recomendación)

Cumplir lo siguiente **no** sustituye los mínimos de la tabla de **Teléfono** arriba, pero Google lo usa para elegibilidad en recomendaciones y promoción.

| Contexto   | Capturas       | Orientación y mínimos sugeridos                                                                                        |
| ---------- | -------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **Apps**   | Al menos **4** | Lado corto mín. **1080** px. **16:9** horizontal mín. **1920 × 1080** px, o **9:16** vertical mín. **1080 × 1920** px. |
| **Juegos** | Al menos **3** | Tres capturas **16:9** (mín. **1920 × 1080** px) **o** tres **9:16** (mín. **1080 × 1920** px).                        |

---

## Resumen rápido: qué subir según tu caso

| Situación                          | Mínimo gráfico alineado con consola (teléfono típico)                                                 |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Solo teléfono                      | Icono **512²** (≤1 MB, PNG/JPEG), gráfico **1024×500** (≤15 MB, PNG/JPEG), **2–8** capturas teléfono. |
| Promoción / recomendaciones (apps) | **4** capturas con mínimos 1080 px / 16:9 o 9:16 de la tabla «Muy recomendado».                       |
| Promoción (juegos)                 | **3** capturas 16:9 o **3** en 9:16 con mínimos de la misma tabla.                                    |
| Tablet 7"                          | Hasta **8** capturas; lados **320–3840** px; 16:9 o 9:16; ≤8 MB.                                      |
| Tablet 10"                         | Hasta **8** capturas; lados **1080–7680** px; 16:9 o 9:16; ≤8 MB.                                     |
| Chromebook                         | **4–8** capturas; lados **1080–7680** px; 16:9 o 9:16; ≤8 MB.                                         |
| XR                                 | Aplica la sección condicional correspondiente.                                                        |

---

## Buenas prácticas breves

- Añade **texto alternativo (alt)** a cada imagen (Google sugiere hasta **140 caracteres**, sin empezar por «foto de…» o «imagen de…»).
- Las capturas deben mostrar la **experiencia real** de la app; evita reclamaciones de ranking, precio o descargas, y CTAs tipo «instala ya» según la [política de metadatos](https://support.google.com/googleplay/android-developer/answer/9898842).
- **Gráfico de funciones:** evita duplicar el mismo protagonismo visual del icono; ten en cuenta zonas de recorte que la interfaz de Play puede aplicar.
