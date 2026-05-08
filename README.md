# app_template_with_flutter

Plantilla base en Flutter para arrancar proyectos nuevos con dependencias mínimas, internacionalización lista y estructura de carpetas clara.

## Flujo de desarrollo y producción

Orden sugerido para pasar del concepto a la publicación:

1. **Diseño visual y bocetos**  
   Definir las pantallas completas con mockups o wireframes de alta fidelidad (por ejemplo con Gemini u otra IA de generación de imágenes), de modo que el flujo y el aspecto general queden cerrados antes de codificar.

2. **Extracción de recursos**  
   Del material de diseño, extraer gráficos e iconos relevantes para la app y ubicarlos en `assets/` (u otra convención del proyecto) para poder referenciarlos desde el código.

3. **Ajuste de assets**  
   Refinar tamaños, formatos y transparencias en herramientas como Inkscape o servicios como iloveimg, manteniendo nombres y carpetas estables para el pipeline de build.

4. **Desarrollo incremental**  
   Implementar por entregas pequeñas: pruebas continuas, funcionalidades mínimas viables, nuevas pantallas según avanza el diseño, y cuando haga falta nuevas extracciones de imagen y su posterior ajuste.

5. **Modelo de negocio**  
   La monetización y el alcance suelen definirse en paralelo al diseño de bocetos; cuando el desarrollo funcional esté completo, integrar el modelo de negocio en la app (suscripciones, compras in-app, anuncios, etc., según lo acordado).

6. **Iteración**  
   Tras integrar el modelo de negocio, revisar UX, estabilidad y cumplimiento; repetir ciclos cortos de desarrollo y prueba solo si es necesario.

7. **Presencia en tiendas (gráficos)**  
   Capturar pantallas reales de la app y, con ayuda de Gemini u otro modelo, generar o retocar las piezas de presencia (feature graphic, capturas promocionales, etc.); ajustarlas manualmente hasta cumplir las guías de cada tienda.

8. **Textos legales y de ficha**  
   Redactar política de privacidad, descripciones y demás textos obligatorios usando como guía los README de cada tienda en `assets/app_store/`, `assets/play_store/` y, si aplica, `assets/web_store/`.

9. **Web de políticas**  
   Publicar la política de privacidad (y enlaces relacionados) en la URL que declararás en las tiendas.

10. **Firma, build y lanzamiento**  
    Seguir el proceso de firma y generación de artefactos; publicar en las tiendas y, en paralelo o después, preparar el módulo o sección promocional en la web de la empresa.

Referencias rápidas en esta plantilla: [Google Play](assets/play_store/README.md), [App Store](assets/app_store/README.md).

## Pasos realizados

1. **Proyecto base** creado con `flutter create`.
2. **`pubspec.yaml`**: comentarios por defecto eliminados, sección mínima y `flutter: generate: true` para generación de localizaciones.
3. **`lib/main.dart`**: eliminado el demo del contador, comentarios de tutorial y lógica de ejemplo; app mínima con un solo mensaje en pantalla.
4. **Internacionalización (`flutter gen-l10n`)**:
   - Dependencias: `flutter_localizations` (SDK), `intl`.
   - Configuración en `l10n.yaml`; plantilla ARB en inglés (`arb/app_en.arb`).
   - **Locales**: español (`es`), inglés (`en`), portugués (`pt`), francés (`fr`), ruso (`ru`), alemán (`de`), chino genérico (`zh`), japonés (`ja`), coreano (`ko`).
   - Clave de ejemplo: `appMessage` (demostración de una cadena traducida).
5. **Estructura de ficheros i18n**:
   - `arb/`: únicamente archivos `.arb` (fuentes de traducción).
   - `lib/l10n/`: únicamente Dart generado; no editar a mano.
6. **`test/widget_test.dart`**: prueba de humo alineada con la app actual (sin contador).
7. **Iconos de launcher (Android e iOS)**:
   - Dependencia de desarrollo: `flutter_launcher_icons`.
   - Fuentes en `assets/icons/` (`app_icon_android.png`, `app_icon_ios.png`); configuración en `pubspec.yaml` bajo `flutter_launcher_icons:`.

## Operativa tras cambiar traducciones

Después de modificar los `.arb` en `arb/`, regenera las clases:

```bash
flutter gen-l10n
```

(O usa tu flujo habitual de build; el código en `lib/l10n/` debe mantenerse coherente con los ARB.)

## Operativa tras cambiar los iconos maestros

Cuando sustituyas los PNG en `assets/icons/`, regenera los recursos nativos:

```bash
dart run flutter_launcher_icons
```

Esto actualiza los iconos en `android/` e `ios/`. Si publicas en App Store y el icono lleva canal alpha, revisa la opción `remove_alpha_ios` en la documentación del paquete.

## Google Play

Plantillas y referencias para ficha de tienda, política de privacidad, notas de versión y versionado: [assets/play_store/README.md](assets/play_store/README.md).

## App Store (iOS)

Pasos para publicar en App Store Connect (firma, build, subida y revisión): [assets/app_store/README.md](assets/app_store/README.md).
