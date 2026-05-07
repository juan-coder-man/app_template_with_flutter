# App Review Information

Sección **Información de revisión de la aplicación** en App Store Connect (**App Store → Versión → App Review Information**). Aquí Apple recibe los datos que necesita el equipo de revisión para evaluar el binario. Se rellena **una sola vez por app** y **no se localiza**: los textos van en un único idioma, normalmente inglés.

| Campo                       | Obligatorio                   | Notas                                                                                                |
| --------------------------- | ----------------------------- | ---------------------------------------------------------------------------------------------------- |
| Sign-in required (checkbox) | Solo si la app requiere login | Si está activado, hay que rellenar **User name** y **Password** de una cuenta demo válida.           |
| User name                   | Si Sign-in required = sí      | Cuenta demo accesible (sin 2FA bloqueante, sin caducidad imprevista).                                |
| Password                    | Si Sign-in required = sí      | Contraseña de la cuenta demo.                                                                        |
| First name                  | Sí                            | Persona de contacto durante la revisión.                                                             |
| Last name                   | Sí                            | Apellido del contacto.                                                                               |
| Phone number                | Sí                            | Formato internacional `+CC NNN NNN NNN`.                                                             |
| Email                       | Sí                            | Buzón monitorizado. Apple escribe aquí si tiene preguntas.                                           |
| Notes                       | Recomendado                   | Hasta **4000** caracteres. Indicaciones para el revisor (cómo entrar, qué probar, casos especiales). |
| Attachment                  | Opcional                      | 1 archivo. Formatos típicos: pdf, jpg, png, mp4, mov, doc.                                           |

> Si la app **no** requiere autenticación, deja Sign-in required desmarcado y omite User name / Password.

---

## Plantilla para copiar y pegar

### Sign-in required

```
☑ Se requiere iniciar sesión
```

### User name

```
demo@example.com
```

### Password

```
DemoPassword123!
```

### First name

```
Juan
```

### Last name

```
Pérez
```

### Phone number

```
+34 600 000 000
```

### Email

```
contacto@example.com
```

### Notes (en-US, recomendado por Apple)

```
[EXAMPLE] This build is a demo template. Use the credentials provided in the Sign-in section to access the main flow.

Steps to review:
1. Open the app and tap "Sign in".
2. Enter the demo credentials shown above.
3. Browse the home screen and the settings tab.

The app does not collect personal data beyond the demo account. Contact the email above for any blocker during review.
```

### Notes (es, copia interna del equipo)

```
[EJEMPLO] Este build es una plantilla de demostración. Usa las credenciales indicadas en la sección Sign-in para acceder al flujo principal.

Pasos para revisar:
1. Abre la app y pulsa «Iniciar sesión».
2. Introduce las credenciales demo indicadas arriba.
3. Recorre la pantalla principal y la pestaña de ajustes.

La app no recoge datos personales más allá de la cuenta demo. Contacta al correo indicado si hay algún bloqueo durante la revisión.
```

### Attachment

```
(Opcional) Adjuntar un PDF con capturas anotadas o un MP4 con un walkthrough corto.
Formatos sugeridos: pdf, jpg, png, mp4, mov, doc.
Tamaño total habitual: hasta unos 50 MB; revisar el límite vigente en la consola.
```

---

## Buenas prácticas

- Usa una **cuenta demo dedicada**: no expongas credenciales reales de empleados.
- Asegúrate de que la cuenta **no caduca** durante la ventana de revisión y que **no requiere 2FA** vía SMS al revisor.
- Si la app tiene flujos detrás de pago o suscripción, indica en **Notes** cómo simular el acceso (códigos sandbox, builds especiales, etc.).
- Mantén el **email de contacto** monitorizado: si Apple escribe y no respondes en 24–48h, suelen rechazar la revisión.
