# QuietAtlas

**QuietAtlas** es un pequeño atlas personal para guardar lugares, notas y rutas de exploración. Esta primera versión funciona como una aplicación estática en el navegador: no necesita servidor ni instalación de dependencias.

## Funciones de esta versión

- Mapa interactivo con OpenStreetMap con cartografía base de Esri y Leaflet.
- Crear y editar lugares manualmente, usando coordenadas o haciendo clic en el mapa.
- Categorías, etiquetas, notas, búsqueda y filtros.
- Importar KML de Google Earth: puntos, líneas y polígonos (estos últimos se guardan como trazados cerrados).
- Exportar la colección a KML.
- Exportar y restaurar una copia de seguridad JSON.
- Guardado local mediante `localStorage` del navegador.
- Diseño adaptable a escritorio y móvil.

## Ejecutar localmente

1. Descarga y descomprime `QuietAtlas.zip`.
2. Abre `index.html` con Firefox, Chrome o Edge.
3. Asegúrate de tener conexión a Internet para cargar Leaflet y los mosaicos del mapa.
4. Importa un `.kml` desde el botón **Importar KML** o crea un lugar con **Nuevo lugar**.

No hay backend. Los datos permanecen en el perfil del navegador donde los guardes. Borrar los datos del sitio/navegador puede eliminarlos; usa **Copia** para guardar un respaldo JSON. El mapa base necesita Internet, aunque los lugares guardados permanecen en el navegador.

### Restaurar una copia JSON

Arrastra un archivo `quietatlas-backup.json` exportado previamente sobre la zona del mapa y confirma la importación. La restauración añade elementos a los existentes y les asigna nuevos identificadores; no los sustituye.

## Estructura del proyecto

```text
QuietAtlas/
├── index.html       # Aplicación completa (HTML, CSS y JavaScript)
├── README.md        # Instrucciones y descripción
├── LICENSE          # Licencia MIT
├── .gitignore       # Archivos locales ignorados por Git
└── sample.kml       # Datos de ejemplo para probar la importación
```

La aplicación está concentrada en un único `index.html` para facilitar el primer uso. Si crece, conviene separar CSS y JavaScript en `styles.css` y `app.js`.

## Tecnologías y atribución

- [Leaflet](https://leafletjs.com/) para el mapa interactivo (cargado desde un CDN).
- [OpenStreetMap con cartografía base de Esri](https://www.openstreetmap.org/copyright) para los mosaicos del mapa. Respeta la atribución visible en el mapa y sus políticas de uso.
- HTML, CSS y JavaScript nativos.

## Prepararlo para GitHub

1. Crea un repositorio nuevo llamado `QuietAtlas` en GitHub. **No reutilices el repositorio de tu mod de Persona 5 Royal.**
2. Sube los archivos de esta carpeta a la raíz del repositorio.
3. En **Settings → Pages**, elige publicar desde la rama `main` y la carpeta `/(root)` si quieres que sea accesible mediante una URL pública.
4. Para uso local, basta con abrir `index.html`; GitHub Pages es opcional.

## Limitaciones conocidas de la primera versión

- Los mosaicos del mapa y las librerías externas requieren conexión a Internet.
- Los datos se guardan en el navegador y no se sincronizan entre dispositivos.
- Se importan geometrías sencillas de KML; estilos, iconos, carpetas, adjuntos y geometrías avanzadas no se conservan.
- Los polígonos KML se representan como líneas cerradas, no como áreas rellenas.
- La aplicación no sube datos a ningún servidor.
