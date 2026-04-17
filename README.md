# app_template_with_flutter

Plantilla base en Flutter para arrancar proyectos nuevos con dependencias mínimas, internacionalización lista y estructura de carpetas clara.

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

## Operativa tras cambiar traducciones

Después de modificar los `.arb` en `arb/`, regenera las clases:

```bash
flutter gen-l10n
```

(O usa tu flujo habitual de build; el código en `lib/l10n/` debe mantenerse coherente con los ARB.)