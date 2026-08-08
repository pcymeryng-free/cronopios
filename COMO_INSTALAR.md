# Ficha de Tenis - Dobles (app instalable)

App web (PWA) para cargar la ficha de estadísticas de un partido de dobles desde el celular y enviarla por WhatsApp al terminar. Funciona en iPhone y en Android, sin pasar por App Store ni Google Play.

Incluye: `index.html`, `manifest.json`, `sw.js`, carpeta `icons/`.

## 1. Publicarla en internet (gratis, 2 minutos)

Un PWA necesita estar en una URL con HTTPS para poder "instalarse" en la pantalla de inicio. Dos opciones simples y gratuitas:

### Opción A — Netlify Drop (la más rápida)
1. Entrá a https://app.netlify.com/drop desde la computadora.
2. Arrastrá la carpeta `ficha-tenis-app` completa (con index.html, manifest.json, sw.js e icons/) a la página.
3. Netlify te da una URL tipo `https://algo-random.netlify.app`. Esa es la dirección de tu app.

### Opción B — GitHub Pages
1. Creá un repositorio nuevo en GitHub y subí el contenido de la carpeta `ficha-tenis-app`.
2. Activá GitHub Pages en Settings → Pages → branch `main` → carpeta `/root`.
3. Tu app queda en `https://tu-usuario.github.io/tu-repo/`.

## 2. Instalarla en el iPhone
1. Abrí la URL en **Safari** (tiene que ser Safari, no Chrome).
2. Tocá el ícono de Compartir (el cuadrado con la flecha hacia arriba).
3. Elegí **"Agregar a pantalla de inicio"**.
4. Confirmá el nombre y tocá **Agregar**.

Va a quedar como una app más, con su ícono, y abre a pantalla completa.

## 3. Instalarla en Android
1. Abrí la URL en **Chrome**.
2. Chrome va a mostrar un aviso **"Agregar Ficha Tenis a la pantalla de inicio"** (o tocá el menú ⋮ → "Instalar app" / "Agregar a pantalla de inicio").
3. Confirmá.

## 4. Uso durante el partido
- Completá fecha, rival, prueba y set.
- Elegí los 4 jugadores (2 por pareja) de la lista de buena fe del club. Si alguno no está en la lista (invitado o rival de otro club), elegí **"✏️ Otro / Invitado"** y escribí el nombre a mano.
- Durante el partido, tocá **+ / −** en cada estadística a medida que ocurre (saques, aces, winners, errores, break points, etc.). Los datos se guardan solos en el celular (aunque cierres la app o te quedes sin señal).
- Al terminar el set/partido, completá el resultado y observaciones.
- Tocá **"📲 Enviar por WhatsApp"**: se abre WhatsApp con el resumen de la ficha ya armado en un mensaje, listo para elegir el contacto o grupo y enviar.
- Tocá **"🔄 Nueva"** para vaciar la planilla y cargar el siguiente set o partido.

## Notas
- No requiere conexión a internet para usarse (una vez instalada, funciona offline gracias al service worker); solo necesita señal en el momento de enviar por WhatsApp.
- Todo se guarda localmente en el celular (localStorage). No hay servidor ni base de datos: nadie más ve los datos hasta que vos los envíes.
- Si en algún momento querés pasar esto a una app nativa "de verdad" (ícono propio en App Store / Google Play), este mismo código HTML/JS se puede envolver con Capacitor o React Native WebView sin rehacer la lógica.
- La lista de jugadores está cargada en el código (`ROSTER` dentro de `index.html`, tomada de la Lista de Buena Fe de Cronopios). Si el plantel cambia, avisame y actualizo la lista.
- Si ya habías instalado una versión anterior de la app, volvé a abrirla con internet una vez para que el service worker actualice la versión con la lista de jugadores (o desinstalá y reinstalá el acceso directo).
