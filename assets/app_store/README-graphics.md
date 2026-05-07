# Activos gráficos para la ficha en App Store

Referencias de tamaños, formatos y cantidades para los activos que App Store Connect pide en **App Store → App Previews and Screenshots** y en **App Information → App Icon**. Los requisitos pueden cambiar; confirma siempre en la ayuda oficial.

Documentación oficial: [Screenshot specifications](https://developer.apple.com/help/app-store-connect/reference/screenshot-specifications/) · [App preview specifications](https://developer.apple.com/help/app-store-connect/reference/app-preview-specifications/) · [App icon](https://developer.apple.com/design/human-interface-guidelines/app-icons).

---

## Mínimo obligatorio

Para enviar a revisión necesitas, al menos:

- **Icono de la app** en el binario (incluido vía `Assets.xcassets/AppIcon.appiconset` en Xcode).
- **Capturas de iPhone 6.5"** (cubre la familia de iPhone más común).
- **Capturas de iPad 13"** (obligatoria si la app es universal o se distribuye en iPad; según la captura adjunta de la consola, es lo que App Store Connect está pidiendo).

| Activo               | Dimensiones admitidas                                          | Formato       | Notas                                                  |
| -------------------- | -------------------------------------------------------------- | ------------- | ------------------------------------------------------ |
| Icono App Store      | **1024 × 1024** px                                             | PNG sin alpha | Sin transparencia ni esquinas redondeadas; sRGB o P3.  |
| Capturas iPhone 6.5" | `1242 × 2688`, `2688 × 1242`, `1284 × 2778` o `2778 × 1284` px | JPEG o PNG    | Hasta **10** capturas + **3** app previews por idioma. |
| Capturas iPad 13"    | `2064 × 2752`, `2752 × 2064`, `2048 × 2732` o `2732 × 2048` px | JPEG o PNG    | Hasta **10** capturas + **3** app previews por idioma. |

> Apple permite reutilizar las capturas de iPhone 6.5" para los demás tamaños de iPhone más pequeños; lo mismo aplica entre tamaños de iPad. Si subes solo el tamaño “mayor” obligatorio, el resto se hereda automáticamente.

---

## Opcional

| Activo                      | Dimensiones admitidas                                                               | Formato                       | Notas                                                                                                    |
| --------------------------- | ----------------------------------------------------------------------------------- | ----------------------------- | -------------------------------------------------------------------------------------------------------- |
| Capturas Apple Watch        | `410 × 502`, `416 × 496`, `396 × 484`, `368 × 448` o `312 × 390` px (según familia) | JPEG o PNG                    | Solo si distribuyes app de Watch.                                                                        |
| App Preview (vídeo)         | Mismas resoluciones que las capturas del dispositivo correspondiente                | MOV, M4V o MP4 (H.264 / HEVC) | Hasta **3** vídeos por dispositivo y por idioma; duración **15–30 s**.                                   |
| Capturas iPhone 6.7" / 6.9" | Resoluciones específicas según familia                                              | JPEG o PNG                    | Recomendado para mostrar correctamente en los modelos más recientes; si se omite, Apple usa las de 6.5". |
| Capturas iPad 11"           | `1668 × 2388` o `2388 × 1668` px                                                    | JPEG o PNG                    | Si se omite, Apple usa las de iPad 13".                                                                  |

---

## Reglas generales

| Requisito                | Valor                                                                                             |
| ------------------------ | ------------------------------------------------------------------------------------------------- |
| Cantidad mínima          | **1** captura por familia obligatoria; recomendado **3–5** para una ficha presentable.            |
| Cantidad máxima          | **10** capturas + **3** app previews por familia y por idioma.                                    |
| Espacio de color         | sRGB o Display P3.                                                                                |
| Profundidad de color     | 24 bits (sin canal alpha en el icono; las capturas pueden tener alpha pero no se recomienda).     |
| Contenido                | Debe reflejar la experiencia real dentro de la app.                                               |
| Prohibido                | Precios, rankings, claims tipo “#1”, “Top App” o llamadas a instalar. No marcos de terceros.      |
| Texto sobre las capturas | Permitido si forma parte del marketing de la propia app y no contradice las normas de App Review. |

---

## Resumen rápido

| Situación                                           | Qué subir como mínimo gráfico                                                                              |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| App solo iPhone                                     | Icono 1024², al menos **1** captura iPhone 6.5" (recomendado 3–5).                                         |
| App universal (iPhone + iPad)                       | Icono 1024², capturas iPhone 6.5" y capturas iPad 13".                                                     |
| Quieres mostrar mejor experiencia en modelos nuevos | Añadir capturas iPhone 6.7"/6.9" e iPad 11" además de las obligatorias.                                    |
| Distribuyes app de Apple Watch                      | Añadir capturas Watch en al menos un tamaño de la familia.                                                 |
| Vas a usar app previews                             | Hasta **3** vídeos por dispositivo y por idioma, **15–30 s**, mismo tamaño que la captura correspondiente. |

---

## Buenas prácticas breves

- Sube primero las capturas en el **idioma primario** (`en-US`); App Store Connect las usará como fallback en el resto si no localizas.
- Mantén el **mismo orden** entre idiomas (la primera captura es la que se ve en resultados de búsqueda).
- No incluyas **información sensible** ni datos personales en las capturas.
- Para apps universales, asegúrate de que las capturas de iPad **no** sean simples reescalados de iPhone: la consola las puede rechazar.
- Verifica antes de subir que las imágenes están en **sRGB** y sin perfil ICC raro; muchos rechazos automáticos vienen de espacios de color no soportados.
