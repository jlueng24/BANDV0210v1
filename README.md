# Diversión con el mundo — versión 3.6

## Subir a GitHub Pages

Descomprime el ZIP y sube **el contenido de esta carpeta** a la raíz del repositorio. `index.html` debe quedar en la raíz, junto a `app.js`, `achievements.js`, `achievements.json` y `countries-local.json`. Conserva la carpeta `img/logros` con sus SVG. GitHub no ejecuta la aplicación si solo subes el archivo ZIP.

Al actualizar un sitio ya publicado, reemplaza los archivos existentes por los de esta versión. El progreso anterior permanece guardado en el navegador del jugador.

## Catálogos

- Europa tiene 45 países en `countries-local.json`, disponible aunque falle la carga mundial.
- El catálogo mundial se obtiene de [mledoze/countries](https://github.com/mledoze/countries), con licencia ODbL 1.0, y se guarda localmente tras una carga correcta. Si esa descarga falla, la aplicación muestra el alcance disponible y permite jugar Europa; no presenta 45 países como si fueran todo el mundo.
- Las banderas se muestran desde FlagCDN. Las imágenes de logros, en cambio, están incluidas en `img/logros`.

## Verificación técnica

Con Node.js instalado, ejecuta `node tests/smoke.cjs` desde esta carpeta. Comprueba el catálogo mundial y su respaldo, preguntas únicas, las repeticiones de repaso en Estudio, las tres variantes finitas de Supervivencia, el reloj por pregunta, los hitos y las victorias, el reto diario y la pausa.

Las partidas normales no repiten país dentro de la misma ronda. En Estudio vuelven las preguntas falladas hasta acertarlas. En Supervivencia se elige Banderas, Capitales o Mixto. La lista se baraja y cada bandera o capital disponible aparece una sola vez; Mixto suma ambas listas. El reloj se reinicia en cada pregunta: 25 s en Niños, 20 s en Adultos y 15 s en Máster. Un error o el reloj agotado termina el intento; acertarlo todo muestra la victoria y desbloquea el título regional o mundial. Los hitos del 25 %, 50 % y 75 % quedan guardados aunque después se pierda. Cada reto y región ocupa una tarjeta con sus cuatro hitos en la Sala de logros. En escritorio, las preguntas muestran la bandera o capital a la izquierda y las respuestas A–D a la derecha; en tablet y móvil se apilan. El reto diario usa la fecha local y conserva exactamente la misma pregunta si se abre de nuevo ese día.
