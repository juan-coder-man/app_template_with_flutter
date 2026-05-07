# Política de privacidad (App Store)

App Store Connect exige una **URL pública y accesible** donde se muestre la política de privacidad. Se introduce en **App Store → App Privacy → Privacy Policy URL** y es obligatoria para enviar a revisión. Puede alojarse en **Google Sites**, otra plataforma o un sitio propio. El repositorio no sustituye asesoría legal: el texto definitivo debe ajustarse a la ley aplicable y, si aplica, revisarse con un profesional.

> Adicionalmente, App Store Connect pide rellenar **Privacy Practices / Data Types** (cuestionario de "Privacy Nutrition Labels") con los datos que recoge la app y su finalidad. Esa parte se completa dentro de la propia consola y no requiere URL externa.

## Campos y responsabilidades

| Campo                             | Descripción                                                                                                                                       |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| **URL pública**                   | Enlace que se pega en App Store Connect (debe abrirse en navegador sin inicio de sesión del usuario final).                                       |
| **Slug / ruta (“endpoint”)**      | Fragmento de la URL tras el dominio (p. ej. `/politicadeprivacidad-nombreproyecto`). Suele coincidir con el nombre lógico de la página o archivo. |
| **Nombre del sitio o proyecto**   | En Google Sites: el nombre que identifica el sitio en la lista de Sites; conviene que sea reconocible para el equipo.                             |
| **Nombre de página / archivo**    | Título o identificador de la página dentro del sitio (en Sites puede alinearse con la ruta visible).                                              |
| **Título visible**                | Encabezado que ven los usuarios (p. ej. «Política de privacidad»).                                                                                |
| **Cuerpo**                        | Texto completo de la política (datos recogidos, finalidad, bases legales, derechos, contacto, etc., según corresponda).                           |
| **Fecha de última actualización** | Fecha en que se actualizó el documento (convención explícita en la propia página).                                                                |

En App Store Connect, la **Privacy Policy URL** se introduce **una vez por idioma** dentro de la información localizada de la versión. Si solo dispones de una versión, puedes pegar la misma URL en todos los idiomas o, si tienes versiones traducidas, usar la que corresponda al idioma de la ficha.

## Plantilla para copiar y pegar

Estructura de ejemplo (Google Sites u otro):

### Nombre del archivo

```
politicadeprivacidad-[nombredetuproyecto]
```

### URL y página

```
https://sites.google.com/view/politicadeprivacidad-[nombredetuproyecto]/inicio
```

### Título visible

```
Política de Privacidad
```

### Cuerpo

```
Aquí va el texto íntegro de la política de privacidad.

En la versión real incluirías datos tratados, finalidades, base legal, conservación, destinatarios, derechos del interesado, contacto del responsable, autoridad de control y lo que exija tu normativa.
```

### Última actualización

```
Última actualización: AAAA-MM-DD
```

Antes de enviar la app a revisión, sustituye los valores de ejemplo y revisa el cuerpo con asesoría si procede. Verifica también que la URL responde con **HTTPS**, sin redirecciones a `login` y sin pedir cookies bloqueantes para mostrar el contenido.
