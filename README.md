# 🦍 Gorilla Arkanoid 🍌

Arkanoid de la jungla en un solo `index.html` (HTML/CSS/JS, sin dependencias).

**Jugar online:** https://answer2002.github.io/gorilla-arkanoid/

## Controles
- Ratón / táctil / flechas: mover la mano de gorila (el ratón tiene aceleración: movimientos rápidos llegan antes, movimientos lentos son precisos).
- Clic o ESPACIO: lanzar el mango.
- Clic o F con la barra llena: **¡FURIA DEL GORILA!** (7 s de mangos en llamas que atraviesan ladrillos y puntos x2).
- P: pausa · M: sonido.

## Mecánicas
- Combos: cada ladrillo roto sin tocar la mano sube el multiplicador (hasta x5).
- Barra de furia: se llena rompiendo ladrillos y combos.
- Power-ups: 🍌 mango gigante, ❤️ vida extra, 💪 mano gigante, 🐌 mango lento, 🍇 lluvia de mangos.

## 🏆 Ranking de mejores gorilas
- Al terminar la partida (game over) el juego pide tu nombre y guarda la puntuación; se muestra el **top 10**. Tecla **R** o el botón 🏆 muestran el ranking en cualquier momento.
- El ranking es **global y compartido** entre todos los que juegan desde la URL pública: se guarda en [textdb.dev](https://textdb.dev) (almacén JSON gratuito, sin registro ni servidor propio). Además se guarda una copia en `localStorage` como caché y respaldo si no hay conexión.
- Cualquiera con la URL del documento puede escribir en él (es un juego entre amigos, no hay anti-trampas).
- Para cambiar de backend (Firebase, Supabase, jsonbin, etc.) solo hay que reescribir `rankingRemoteLoad()` y `rankingRemoteSave()` en `index.html` (reciben/devuelven un array de `{ name, score, level, date }`). Para empezar un ranking nuevo en textdb.dev, basta con poner otro UUID en `RANKING.url`.
