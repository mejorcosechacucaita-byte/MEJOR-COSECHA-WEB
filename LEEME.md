# Mejor Cosecha — Página web

Guía para **publicar** la página, **alimentarla** con productos/fotos/videos y **conectar un dominio**.
No necesitas saber programar. Todo se hace desde la página de GitHub, arrastrando archivos.

---

## 1) ¿Qué hay en esta carpeta?

```
index.html                 ← la página (no necesitas tocarla casi nunca)
LEEME.md                   ← este instructivo
data/
  productos.js             ← AQUÍ agregas o quitas productos
  galeria.js               ← AQUÍ agregas fotos y videos del slider
assets/
  logo-blanco.png          ← el logo
  local.jpg                ← foto del almacén
  productos/               ← una foto por producto
  galeria/                 ← fotos y video del slider
```

La idea: **las fotos van en las carpetas `assets/…` y en los archivos `data/…` escribes qué mostrar.**

---

## 2) Subir la página a GitHub (gratis) y publicarla

**a. Crear la cuenta y el repositorio**
1. Entra a https://github.com y crea una cuenta gratis.
2. Arriba a la derecha, botón **+** → **New repository**.
3. En *Repository name* escribe: `mejor-cosecha`. Déjalo en **Public**. Clic en **Create repository**.

**b. Subir los archivos**
1. En el repositorio nuevo, clic en **Add file → Upload files**.
2. Arrastra **todo lo que hay dentro de esta carpeta** (el `index.html`, la carpeta `data` y la carpeta `assets`). 
   - Truco: selecciona `index.html`, `data` y `assets` juntos y suéltalos en la ventana.
3. Abajo, clic en **Commit changes**.

**c. Encender la página (GitHub Pages)**
1. En el repositorio ve a **Settings** (Configuración) → en el menú izquierdo, **Pages**.
2. En *Source* elige **Deploy from a branch**.
3. En *Branch* elige **main** y la carpeta **/ (root)**. Clic en **Save**.
4. Espera 1–2 minutos y recarga. Aparecerá tu dirección:
   **https://TU-USUARIO.github.io/mejor-cosecha/**

¡Listo! Esa ya es tu página en internet. Compártela por WhatsApp para probarla.

---

## 3) Cómo AGREGAR PRODUCTOS

1. Toma la **foto del producto** (de frente, fondo claro) y ponle un nombre sencillo sin espacios,
   por ejemplo `nuevo-producto.jpg`.
2. En GitHub entra a la carpeta `assets/productos` → **Add file → Upload files** → sube la foto.
3. Entra al archivo `data/productos.js` → clic en el **lápiz** (Edit) arriba a la derecha.
4. Copia una línea existente y pégala. Cambia el nombre, la categoría y la foto. Ejemplo:

```js
  { nombre: "Nuevo Producto", categoria: "fungicidas", foto: "assets/productos/nuevo-producto.jpg" },
```

   - **categoria** solo puede ser: `nutricion`, `fungicidas`, `insecticidas` o `herbicidas`.
   - Respeta las **comillas** y la **coma** al final.
5. Abajo, **Commit changes**. En 1 minuto el producto aparece solo en el catálogo.

Para **quitar** un producto: edita `data/productos.js` y borra su línea.

---

## 4) Cómo AGREGAR FOTOS o VIDEOS al slider (Galería)

1. Sube la foto o el video (`.mp4`) a la carpeta `assets/galeria` (Add file → Upload files).
2. Edita `data/galeria.js` (lápiz) y agrega una línea:

**Foto:**
```js
  { tipo: "foto", archivo: "assets/galeria/mi-foto.jpg", titulo: "Mi título", texto: "Una frase corta." },
```

**Video:**
```js
  { tipo: "video", archivo: "assets/galeria/mi-video.mp4", portada: "assets/galeria/mi-foto.jpg", titulo: "Mi título", texto: "Una frase corta." },
```
   (la *portada* es opcional; es la imagen que se ve antes de darle play).
3. **Commit changes**. El slider se actualiza solo.

> Consejo: para que el video pese poco y cargue rápido, que dure menos de ~30 segundos.

---

## 5) Cómo AGREGAR VIDEOS DE TIKTOK

En la sección de videos ya está uno de tus TikTok. Para agregar otro:
1. En TikTok abre el video → **Compartir → Copiar enlace**. El enlace termina en un número largo,
   por ejemplo `.../video/7597147609819581752`. Ese número es el **ID**.
2. Edita `index.html`, busca la palabra `tiktok-embed` y verás un bloque como este:

```html
<blockquote class="tiktok-embed" cite="https://www.tiktok.com/@mejorcosecha/video/7597147609819581752" data-video-id="7597147609819581752" style="max-width:325px;min-width:280px;margin:0"><section></section></blockquote>
```
3. Cópialo y pégalo justo debajo, cambiando **las dos veces** que aparece el número por el ID de tu nuevo video.
4. **Commit changes**.

---

## 6) Comprar un dominio propio (ej. mejorcosecha.com)

Un dominio cuesta aprox. **US$10–15 al año**. Puedes comprarlo en:
Namecheap, GoDaddy, Cloudflare o Hostinger.

**Conectarlo a tu página de GitHub:**

1. En tu repositorio: **Add file → Create new file**. Nómbralo exactamente `CNAME`
   (sin extensión) y adentro escribe solo tu dominio, por ejemplo:
   ```
   mejorcosecha.com
   ```
   Guarda (Commit).
2. En el panel de tu dominio (donde lo compraste), en la parte de **DNS**, agrega:
   - Cuatro registros tipo **A** apuntando a estas IP de GitHub:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - Un registro tipo **CNAME** con nombre `www` que apunte a `TU-USUARIO.github.io`
3. En GitHub → **Settings → Pages → Custom domain**, escribe tu dominio y **Save**.
   Marca la casilla **Enforce HTTPS** (puede tardar unas horas en habilitarse).
4. Espera un rato (el DNS puede tardar de minutos a 24 horas). Luego tu página abrirá en
   **https://mejorcosecha.com** 🎉

---

## Datos actuales de la página (por si quieres cambiarlos)

- Teléfono / WhatsApp: **310 297 0055**
- Dirección: **DG 6 #1-18, Centro, Cucaita, Boyacá**
- Correo: **mejorcosechacucaita@gmail.com**
- Horario: **Lunes a sábado · hasta 6:00 p.m.** (ajústalo si cambia)

Estos textos están dentro de `index.html`. Si necesitas cambiarlos y no te sientes cómodo
editándolos, me dices y te digo exactamente qué línea tocar.

> Nota: los **nombres de los productos** se leyeron de tus fotos. Revísalos en `data/productos.js`
> y corrige el que no coincida.
