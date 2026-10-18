# Piedra, papel o tijeras

![Piedra, papel o tijeras](./assets/juegoPP-TJS_h2fd9s.jpg)

Juego web clásico de **piedra, papel o tijeras**: tú contra la máquina, al mejor de cinco rondas. Construido con HTML, CSS y JavaScript sin dependencias de build, listo para desplegar como sitio estático.

[![Demo en vivo](https://img.shields.io/badge/demo-en%20vivo-0FA396?style=flat-square)](https://rock-paper-scissor-puce-eight.vercel.app)
[![HTML](https://img.shields.io/badge/HTML-5-e34f26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![CSS](https://img.shields.io/badge/CSS-3-1572b6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/es/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6-f7df1e?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/es/docs/Web/JavaScript)

**Demo:** https://rock-paper-scissor-puce-eight.vercel.app

## Características

- Duelo **usuario vs. CPU** con marcador al primero en llegar a **3 puntos** (al mejor de cinco).
- La CPU elige su jugada de forma aleatoria y uniforme.
- Cada ronda muestra la **regla aplicada** (por ejemplo, "La piedra aplasta las tijeras.").
- Indicadores visuales de progreso (pips) y comunicación del veredicto con `aria-live`.
- Diálogo de fin de partida con el marcador final y opción de jugar de nuevo.
- Diseño responsivo, con soporte para `prefers-reduced-motion`.

## Cómo ejecutar

No requiere instalación ni proceso de build. Solo abre `index.html` en tu navegador:

```bash
git clone https://github.com/JhoamSebastianMunoz/rock-paper-scissors-react.git
```

Luego abre el archivo `index.html` con doble clic. Las únicas dependencias se cargan por CDN:

- [SweetAlert2](https://sweetalert2.github.io/) para los diálogos.
- Google Fonts (*Big Shoulders Display* y *Archivo*).

> [!TIP]
> ¿Prefieres un servidor local? Desde la raíz del proyecto puedes usar cualquier servidor estático, por ejemplo `npx serve` o la extensión Live Server de VS Code.

## Reglas

- El usuario elige **piedra**, **papel** o **tijeras**; la CPU elige al azar.
- Piedra vence a tijeras, tijeras vence a papel y papel vence a piedra.
- Gana la partida quien primero alcance **3 puntos**. Los empates no suman.

## Estructura del proyecto

| Archivo | Descripción |
|---------|-------------|
| `index.html` | Estructura de la interfaz (arena, marcadores y botones de jugada) |
| `style.css` | Estilos, variables de color, responsividad y accesibilidad |
| `app2.js` | Lógica del juego |
| `assets/` | Iconos de piedra, papel y tijeras, banner e imagen del juego |

## Lógica del juego (`app2.js`)

- `choices`: mapea cada opción con su nombre, imagen y a qué opción vence (`beats`).
- `userPlay(choice)`: registra la jugada del usuario y obtiene la de la CPU.
- `getCpuChoice()`: elige una opción aleatoria de forma uniforme.
- `determineWinner()`: compara las jugadas y suma el punto al ganador o declara empate.
- `checkForGameWinner()`: si alguien llega a 3, deshabilita botones, muestra el ganador y resetea.
- `resetGame()`: reinicia marcadores, imágenes y estado.

## Diseño

Interfaz de duelo (usuario contra la CPU) con marcador "primero a 3".

- **Paleta derivada de los iconos del juego:** tinta `#0E1A1F`, panel `#16262C`, giza `#F1EFE7`, usuario (verde azulado) `#0FA396`, CPU (rojo) `#D93A2B`, empate (lima) `#A6CE39`.
- **Tipografía:** *Big Shoulders Display* (títulos, marcador y veredicto) + *Archivo* (texto de interfaz).
- **Responsivo:** a partir de 780 px los esquineros se muestran en paralelo separados por el "vs"; por debajo se apilan en columna, con los botones de jugada al alcance del pulgar.
- **Accesibilidad:** el veredicto se anuncia con `aria-live`, los botones de jugada tienen `aria-label` y foco visible; se respeta `prefers-reduced-motion`.

## Despliegue

El proyecto es un sitio estático y está desplegado en Vercel:

**[https://rock-paper-scissor-puce-eight.vercel.app](https://rock-paper-scissor-puce-eight.vercel.app)**

Para desplegar tu propia copia puedes importar el repositorio en Vercel o publicarlo en cualquier hosting de sitios estáticos (GitHub Pages, Netlify, etc.) sin configuración adicional.
