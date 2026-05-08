# Activos gráficos para la ficha en App Store

Referencias según los textos y campos que muestra **App Store Connect** en **App Store → Previews and Screenshots** (pestañas iPhone, iPad y Apple Watch) y en **App Information** para el icono. Los requisitos pueden cambiar; confirma siempre en la ayuda oficial.

Documentación oficial: [Screenshot specifications](https://developer.apple.com/help/app-store-connect/reference/screenshot-specifications/) · [App preview specifications](https://developer.apple.com/help/app-store-connect/reference/app-preview-specifications/) · [App icon](https://developer.apple.com/design/human-interface-guidelines/app-icons).

---

## Icono para App Store _(obligatorio)_

Se configura en **App Information** / asset del icono de marketing (y el binario incluye el icono de la app vía `Assets.xcassets/AppIcon.appiconset` en Xcode).

| Requisito     | Valor                                                                                          |
| ------------- | ---------------------------------------------------------------------------------------------- |
| Dimensiones   | **1024 × 1024** px                                                                             |
| Formato       | **PNG** sin canal alpha                                                                        |
| Aspecto       | Sin transparencia ni esquinas redondeadas en el archivo; Apple aplica la máscara en la tienda. |
| Espacio color | **sRGB** o **Display P3**                                                                      |

---

## Capturas por tipo de dispositivo

En **Previews and Screenshots** cada pestaña (**iPhone**, **iPad**, **Apple Watch**) tiene sus dimensiones y contadores propios. Orientación: **vertical u horizontal** según los pares ancho × alto indicados.

### iPhone 6.5" Display _(obligatorio para poder enviar a revisión en la mayoría de fichas iPhone)_

Si falta, App Store Connect puede impedir **Add for Review** con un mensaje del tipo: «You must upload a screenshot for **6.5-inch iPhone displays**.»

| Requisito           | Valor                                                                                                  |
| ------------------- | ------------------------------------------------------------------------------------------------------ |
| Cantidad capturas   | Hasta **10** por idioma/localización                                                                   |
| Cantidad previews   | Hasta **3**                                                                                            |
| Formato             | **JPEG** o **PNG**                                                                                     |
| Dimensiones válidas | **1242 × 2688** · **2688 × 1242** · **1284 × 2778** · **2778 × 1284** px (retrato o paisaje según par) |

---

### iPad 12.9" / 13" Display _(obligatorio si tu app debe mostrar capturas de iPad; suele exigirse para universal o presencia en iPad)_

Si falta, App Store Connect puede impedir **Add for Review** con: «You must upload a screenshot for **13-inch iPad displays**.»

| Requisito           | Valor                                                                                                                                        |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Cantidad capturas   | Hasta **10**                                                                                                                                 |
| Cantidad previews   | Hasta **3**                                                                                                                                  |
| Formato             | **JPEG** o **PNG**                                                                                                                           |
| Dimensiones válidas | **2064 × 2752** · **2752 × 2064** · **2048 × 2732** · **2732 × 2048** px (retrato o paisaje según par; la consola etiqueta retrato/paisaje). |

---

### Apple Watch _(solo si publicas app de watchOS)_

| Modelo / familia | Dimensiones admitidas (px)    |
| ---------------- | ----------------------------- |
| Ultra 3          | **422 × 514** u **410 × 502** |
| Series 11        | **416 × 496**                 |
| Series 9         | **396 × 484**                 |
| Series 6         | **368 × 448**                 |
| Series 3         | **312 × 390**                 |

| Requisito         | Valor                                         |
| ----------------- | --------------------------------------------- |
| Cantidad capturas | Hasta **10** en total para estos dispositivos |
| Formato           | **JPEG** o **PNG**                            |

---

## Envío a revisión: requisitos gráficos mínimos

Cuando faltan capturas obligatorias, la consola muestra un aviso tipo **Unable to Add for Review** y lista, entre otros, que debes subir captura para **13-inch iPad displays** y para **6.5-inch iPhone displays** cuando correspondan a tu producto.

---

## Reglas generales (capturas e icono)

| Requisito        | Valor                                                                                           |
| ---------------- | ----------------------------------------------------------------------------------------------- |
| Cantidad mínima  | Al menos **1** captura por familia obligatoria; recomendado **3–5** para una ficha clara.       |
| Cantidad máxima  | **10** capturas + **3** app previews por familia de dispositivo y localización (según pestaña). |
| Espacio de color | **sRGB** o **Display P3**.                                                                      |
| Icono App Store  | Sin alpha; las capturas pueden llevar alpha pero no suele recomendarse.                         |
| Contenido        | Debe reflejar la experiencia real en la app.                                                    |
| Prohibido        | Precios, rankings, «#1», llamadas a instalar; marcos de terceros según App Review.              |

Apple permite heredar capturas del tamaño «principal» a tamaños menores del mismo tipo de dispositivo cuando la consola lo ofrezca; revisa **Media Manager** para el mapeo exacto.

---

## Resumen rápido: qué subir según tu caso

| Situación                        | Mínimo gráfico alineado con consola                                                                                            |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Solo iPhone                      | Icono **1024²** (PNG sin alpha); al menos **1** captura **iPhone 6.5"** en un tamaño válido de la tabla (recomendado **3–5**). |
| iPhone + iPad (universal / iPad) | Lo anterior **más** al menos **1** captura **iPad 13"** / 12.9" en un tamaño válido de la tabla.                               |
| Apple Watch                      | Hasta **10** capturas en al menos un tamaño de modelo listado arriba.                                                          |
| App Previews                     | Hasta **3** vídeos por pestaña de dispositivo; misma resolución que las capturas de ese slot; **15–30 s**.                     |

---

## Buenas prácticas breves

- Sube primero material en el **idioma primario** de la ficha; el resto puede heredar hasta que localices.
- Mantén el **mismo orden** de capturas entre idiomas (la primera es la más visible en resultados).
- No incluyas **datos personales** ni información sensible en las capturas.
- En apps **universal**, evita que las capturas de iPad sean solo un reescalado de iPhone si la experiencia difiere.
- Exporta en **sRGB** y perfil ICC estándar para reducir rechazos automáticos por color.
