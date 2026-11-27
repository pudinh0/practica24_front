¿cuáles son los tres requisitos de una PWA y qué hace cada uno?
HTTPS:
Proporciona el contexto seguro para funciones como el registro del service worker
Manifest:
Archivo que define el nombre, icono, colores y comos e abre la app al instalarla
Service worker:
Script que puede gestionar la cache y peticiones, ofrece la funcion
como cargar el contenido guardado sin conexion

¿qué archivos generó vite-plugin-pwa en dist/ y para qué sirve cada uno?
manifest.webmanifest:
contiene los metadatos de la instalacion

sw.js:
administra el cache

workbox-xxxx.js:
contiene la libreria de workbox que usa el service worker para gestionar la cache

registerSW.js:
registra sw.js en el navegador

index.html:
la pagina principal, actualizada para enlazar el manifiesto y registrar
el service worker.

¿por qué las clases usan NetworkFirst y las imágenes CacheFirst?

las clases usan networkFirst por que sus datos pueden cambiar,

las imagenes usan cacheFirst porque suelen no cambiar o es raro que lo hagan, se cargan desde la cache
para ahorrar tiempo y datos, en caso de no estar guardadas se descargan de la red 


¿qué diferencia hay entre una PWA y una aplicación híbrida?
PWA:
una aplicacion web que se puede instalar desde navegador y funciona con tecnologias web,
sus funciones se limitan a lo que el navegador permita

App Hibrida:
Tambien suele usar tecnologias web para la interfaz, pero se empaqueta dentro de una aplicacion navita, se puede
distribuir en tiendas y acceder a funciones del dispositivo mediante complementos o puentes nativos

¿por qué en npm run dev no hay service worker?
Debido a que esta desactivado para evitar que su cache interfiera con los cambios rapidos de vite, para probar
se ejecuta el npm run build y despues npm run preview.