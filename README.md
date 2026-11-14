# Mis Colecciones

Página de inicio (GitHub Pages) que reúne todas mis colecciones:

| Colección   | Hoja de Google            | Estado          |
|-------------|---------------------------|-----------------|
| 🎮 Videojuegos | App Videojuegos          | Apps Script     |
| 💿 Vinilos     | App Colecciones Vinilo   | Apps Script     |
| 🎬 Películas   | Películas                | Por actualizar  |
| 📚 Cómics      | —                        | Por crear       |

## Añadir o cambiar una app
Edita el array `COLECCIONES` al principio del `<script>` de `index.html` y pega la URL `/exec` de la web app.

## Para que una app se vea *dentro* de Mis Colecciones
En el `doGet()` de cada Apps Script, la salida tiene que permitir iframes:

```js
function doGet(e) {
  return HtmlService.createHtmlOutputFromFile('index')   // o createTemplateFromFile(...).evaluate()
    .setTitle('Mi colección')
    .addMetaTag('viewport', 'width=device-width, initial-scale=1')
    .setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL);
}
```

Después: **Implementar → Gestionar implementaciones → editar → Nueva versión**, para que la URL `/exec` sirva el cambio.
Si alguna app da problemas embebida (por ejemplo, pide iniciar sesión), pon `modo:'aparte'` y se abrirá en pestaña nueva.
