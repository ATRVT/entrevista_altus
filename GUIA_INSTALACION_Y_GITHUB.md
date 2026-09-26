# 🚀 Guía de Instalación: Conectar Google Sheets y Publicar en GitHub

¡Felicidades! Tu cuestionario digital de **Anamnesis Clínica Altus** ya está completamente programado, con diseño moderno, fondo blanco `#FFFFFF`, paleta de colores institucional (Azul `#385da9`, Amarillo `#faac3c`, Rojo `#e5442a`), adaptación total para celulares, guardado automático y firma táctil digital.

Sigue estos sencillos pasos para dejarlo 100% operativo y compartirlo con cualquier familia:

---

## 📑 Paso 1: Configurar tu Google Sheets (Solo toma 3 minutos)

Para que las respuestas de las familias se registren automáticamente en una hoja de cálculo en tiempo real:

1. Abre tu navegador y crea una nueva hoja en [Google Sheets](https://sheets.new).
2. Ponle un nombre a tu hoja (por ejemplo: `Respuestas Anamnesis Altus`).
3. En el menú superior de Google Sheets, ve a:
   **Extensiones** > **Apps Script**.
4. Se abrirá el editor de código. Borra cualquier texto que aparezca (`function myFunction() {...}`) y **pega todo el contenido del archivo `google_sheets_script.gs`** que te dejamos en esta carpeta.
5. Haz clic en el icono de guardar (**💾 Guardar proyecto**).
6. En la esquina superior derecha, haz clic en el botón azul **Implementar** > **Nueva implementación**.
7. En la ventana emergente, haz clic en el icono del engranaje ⚙️ (*Seleccionar tipo*) y elige **Aplicación web**.
8. Configura los siguientes campos:
   - **Descripción**: `Receptor Anamnesis Altus`
   - **Ejecutar como**: `Yo (tu correo de Google)`
   - **Quién tiene acceso**: `Cualquier persona` *(⚠️ Muy importante: debe decir "Cualquier persona" para que los papás puedan enviar sus respuestas desde cualquier celular sin necesidad de iniciar sesión en Google)*.
9. Haz clic en el botón azul **Implementar**.
10. Google te pedirá revisar permisos:
    - Haz clic en *Autorizar acceso*.
    - Selecciona tu cuenta de Google.
    - Si te aparece la advertencia *"Google no ha verificado esta app"*, haz clic abajo en **Avanzado** (o *Configuración avanzada*) y luego en **Ir a Proyecto (no seguro)**.
    - Haz clic en **Permitir**.
11. ¡Listo! Google te mostrará una **URL de la aplicación web** (termina en `/exec`). **Copia esa URL**.

---

## 🔗 Paso 2: Vincular la URL en tu Cuestionario

Tienes dos formas muy sencillas de colocar la URL:

### Opción A (La más fácil y visual):
1. Abre tu cuestionario en el navegador.
2. Ve al pie de página (abajo del todo) y haz clic en **⚙️ Configuración de Google Sheets**.
3. Pega la URL que copiaste y pulsa **Guardar cambios**. ¡Quedará guardada en el navegador!

### Opción B (Permanente para todas las familias):
Abre el archivo `app.js` y en la línea 12 coloca tu URL entre las comillas:
```javascript
const DEFAULT_SCRIPT_URL = "https://script.google.com/macros/s/TU_CODIGO_AQUI/exec";
```
De esta manera, cualquier familia que abra el enlace ya lo tendrá conectado automáticamente.

---

## 🌐 Paso 3: Alojamiento en GitHub (¿Es necesario y recomendable?)

> **Sí, es 100% recomendable**.
> Alojar la anamnesis en **GitHub Pages** tiene enormes ventajas:
> - **Totalmente Gratis**: No pagas servidores ni hosting.
> - **Seguridad y Confidencialidad**: Cuenta con certificado SSL oficial (`https://`), lo cual da confianza profesional a los padres de familia.
> - **Compatibilidad Universal**: Se abre al instante desde Safari en iPhone, Chrome en Android, tabletas o computadoras sin instalar ninguna aplicación.
> - **Enlace corto y directo**: Te brinda un link limpio (ejemplo: `https://tu-usuario.github.io/AP_Entrevista/`) listo para enviar por WhatsApp o correo.

### ¿Cómo publicarlo en GitHub Pages en 4 pasos?

1. **Subir los archivos a tu repositorio de GitHub**:
   En tu terminal dentro de esta carpeta, ejecuta:
   ```bash
   git init
   git add .
   git commit -m "Anamnesis Altus digital lista para celular"
   git branch -M main
   # Si creas un repositorio en github.com:
   git remote add origin https://github.com/TU_USUARIO/AP_Entrevista.git
   git push -u origin main
   ```

2. **Activar GitHub Pages**:
   - En tu repositorio en GitHub, ve a la pestaña **Settings** (Configuración).
   - En el menú izquierdo, haz clic en **Pages**.
   - En la sección **Build and deployment**:
     - *Source*: Selecciona **Deploy from a branch**.
     - *Branch*: Elige `main` y la carpeta `/ (root)`.
   - Haz clic en **Save** (Guardar).

3. **¡Listo!** En 1 o 2 minutos, GitHub te dará tu enlace oficial:
   `https://TU_USUARIO.github.io/AP_Entrevista/`

---

## 📲 Paso 4: ¿Cómo compartirlo con las familias?

Solo debes copiar tu enlace de GitHub Pages y enviárselo a los padres de familia con un mensaje cordial como este:

> *"Estimada familia: Les compartimos el enlace para completar la entrevista inicial y anamnesis de su hijo/a previa a nuestra primera sesión: [TU ENLACE AQUÍ]. Pueden responderlo cómodamente desde cualquier celular. Sus respuestas se guardan automáticamente. ¡Muchas gracias!"*
