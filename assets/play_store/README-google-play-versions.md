# Versiones y Google Play

## Campo en `pubspec.yaml`

La línea `version` usa el formato de Flutter:

```yaml
version: X.Y.Z+N
```

| Parte                | Nombre habitual                             | Significado                                                                                                          |
| -------------------- | ------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `X.Y.Z`              | **Version name** (`versionName` en Android) | Versión semántica visible para usuarios (p. ej. `1.0.0`).                                                            |
| `N` (después de `+`) | **Version code** (`versionCode` en Android) | Entero positivo que **debe aumentar** en cada subida nuevo a Google Play (cada track que reciba un artefacto nuevo). |

## Relación con Play Console

Al crear un release en Google Play aparece habitualmente:

- **Nombre del release / título del release**: etiqueta interna que eliges para identificar la entrega (p. ej. «1.0.1 corrección login»). No tiene por qué coincidir literalmente con `version name`, pero conviene que sea coherente para el equipo.
- **Version name del bundle**: Flutter la toma del segmento `X.Y.Z` del `pubspec.yaml` al ejecutar `flutter build appbundle`.
- **Version code del bundle**: Flutter la toma del número `N` después de `+`.

Cada archivo **AAB** que subas debe llevar un **version code** estrictamente mayor que el último aceptado en ese app ID (por política de Google Play).

## Ejemplos (solo ilustrativos)

Orden recomendado al documentar releases en el equipo o en tablas históricas: **del más reciente al más antiguo** (como suele hacerse en changelogs).

| Ejemplo de título del release en Google | Línea `version` en `pubspec.yaml` | Version name | Version code |
| --------------------------------------- | --------------------------------- | ------------ | ------------ |
| `[EJEMPLO] Parche textos y crash fix`   | `1.0.1+2`                         | `1.0.1`      | `2`          |
| `[EJEMPLO] Primera subida tienda`       | `1.0.0+1`                         | `1.0.0`      | `1`          |

Para un nuevo release: incrementa `N` siempre; cambia `X.Y.Z` cuando corresponda según tu política de versionado del producto.
