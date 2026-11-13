# COGA-MAN: Escape de los Profes 🎮

**TP 2: Hacé tu juego** — Prof. Luis Pandiani

**Integrantes:** Nicolas Barrales, Santiago Orlando y Morea Mateo  
**Curso:** 6to 3ra

## 🎮 Jugar

Podés jugar de dos maneras:

1. **Online (GitHub Pages):** entrá a **[Jugar COGA-MAN](https://moreamateo.github.io/CogaMan/)** y presioná **Jugar**. Después elegí **PC** o **celular**. Este enlace funciona una vez activado GitHub Pages en el repositorio.
2. **Descargando el juego:** entrá al [repositorio de COGA-MAN](https://github.com/Moreamateo/CogaMan), descargá el archivo `index.html` (o el ZIP del repositorio), buscá el archivo en tu dispositivo y abrilo con un navegador como Chrome.

No requiere instalar programas adicionales, servidor ni otras carpetas: todo está integrado en el mismo archivo HTML. Se puede jugar desde una computadora o un celular.

## 🤖 IA utilizada

**ChatGPT — GPT-6.**

## 📝 Brief (pedido a la IA)

> Queremos crear COGA-MAN, un juego inspirado en Pac-Man con HTML, CSS y JavaScript, todo dentro de un único `index.html` y adaptable a PC y celular. El jugador controla a Coga usando un sprite de cuatro direcciones y cuatro cuadros por dirección. Debe juntar puntos en un laberinto y escapar de Walter, Lucho, Kevin y Silva, que aparecen como fantasmas pixel art, salen por turnos de una casa central y tienen comportamientos diferentes. Incluí túneles laterales que transporten al jugador de un extremo al otro, tres vidas, puntaje visible, récord, un límite de tiempo, cerezas, poderes temporales, sonidos, menú principal, pantalla de instrucciones, pausa, animaciones y pantallas de victoria y derrota. El juego debe ser desafiante pero posible de completar.

## 🎨 Diseño

COGA-MAN es un juego arcade de laberintos protagonizado por nuestro amigo Coga. El jugador lo mueve por un mapa recogiendo puntos mientras intenta escapar de los profesores Walter, Lucho, Kevin y Silva. Los cuatro enemigos empiezan dentro de una sala central y salen por turnos; cada uno persigue de manera distinta. Coga puede atravesar túneles laterales, conseguir cerezas y activar el modo recreo con bolitas especiales. Comienza con tres vidas y tiene 150 segundos para completar el recorrido. Se gana al juntar todos los puntos y se pierde al quedarse sin vidas o cuando se termina el tiempo.

## ✨ Mejoras visuales y animaciones (actualización)

Además de la jugabilidad y las funciones originales, mejoramos el aspecto del juego para que los personajes y objetos se vean como sprites auténticos de arcade:

- **Fondos eliminados:** limpiamos los fondos del logo, botones, sprites de Coga, profesores, caras, objetos extra, modo poder y modo muerte. El logo ya no muestra texto residual del fondo.
- **Spritesheets centrados:** ajustamos el contenido dentro de cada cuadro de animación de Coga, Walter, Lucho, Kevin, Silva y de los modos poder y muerte, evitando que se desplacen o salten visualmente entre cuadros.
- **Puntos más visibles:** creamos un sprite nuevo de **24 × 24 píxeles**, que en el laberinto se dibuja a **14 × 14 píxeles**. Antes el punto era muy pequeño y se mostraba aproximadamente a 10 × 10. También agrandamos el dibujo alternativo usado cuando falla la carga de la imagen.
- **Bolita especial mejorada:** ahora el *power pellet* tiene un tamaño visual aproximado de **18 píxeles**, más brillo y un efecto luminoso más claro.
- **Cerezas:** limpiamos y centramos el sprite; se muestra a **26 × 26 píxeles**.
- **Modo poder de Coga:** incorporamos su propia secuencia de sprites azulados y animaciones especiales cuando obtiene una bolita de poder.
- **Modo muerte de Coga:** añadimos una secuencia de expresiones pixel art para los momentos de derrota y las pantallas finales.
- **Menús y objetos:** sumamos los recursos visuales de puntos, poder y cerezas al menú y a las instrucciones, sin perder el logo, las opciones principales ni los controles.
- **Experiencia arcade:** se conservan los fantasmas animados, la casa central, túneles laterales, puntaje, vidas, temporizador, sonidos y pantallas de victoria y derrota.

**Detalles técnicos del dibujo:** puntos a `14×14`, bolitas de poder de aproximadamente `18 px` y cerezas a `26×26`. Los gráficos están embebidos dentro de `index.html`, sin archivos de imagen externos.

## 🌳 Árbol de decisión

```
INICIO → Menú principal
    ├── Cómo jugar → Instrucciones → Menú
    ├── Récord → Mejor puntaje → Menú
    └── Jugar → Elegir PC o celular → Comienza la partida
          |
          ├── ¿Coga comió un punto?
          |       └── Sí → Sumar puntaje
          |
          ├── ¿Tomó un poder?
          |       └── Sí → Modo recreo: puede atrapar fantasmas
          |
          ├── ¿Un fantasma atrapó a Coga sin poder?
          |       ├── Sí → Pierde una vida
          |       |        ├── Quedan vidas → Continuar
          |       |        └── No quedan → FIN: DERROTA
          |       └── No → Continuar
          |
          ├── ¿Terminó el tiempo?
          |       └── Sí → FIN: DERROTA
          |
          └── ¿Recogió todos los puntos?
                  └── Sí → FIN: VICTORIA
```

## 🛠️ ¿Qué corregimos de la IA?

1. **Movimiento trabado:** reemplazamos el movimiento rígido por desplazamiento continuo entre casilleros y animaciones con los 16 cuadros del sprite de Coga.
2. **Laberinto demasiado difícil y luego demasiado fácil:** modificamos el mapa para que haya obstáculos, más cruces, caminos alternativos y todos los puntos sean alcanzables.
3. **Fantasmas sin salida:** agregamos una casa central donde los cuatro profesores esperan y salen por turnos mediante una puerta.
4. **Interfaz muy cargada:** quitamos las explicaciones laterales, agrandamos el tablero y pasamos las instrucciones a un menú separado.
5. **Personalización:** agregamos sprites pixel art de los profesores, incluidos los nuevos de Walter y Kevin, y los efectos de sonido y finales.
6. **Fondos en las imágenes:** eliminamos fondos y restos de texto de las imágenes del logo, botones, personajes, objetos y efectos para integrarlos mejor con el diseño del juego.
7. **Sprites que saltaban entre cuadros:** centramos los cuadros de animación de los personajes y de los modos especiales para conseguir transiciones más uniformes.
8. **Objetos difíciles de ver:** agrandamos los puntos y ajustamos el brillo y tamaño de la bolita de poder y las cerezas.
9. **Modos especiales poco diferenciados:** añadimos sprites propios para el modo poder y la secuencia de muerte de Coga, tanto en el juego como en la interfaz.

## 🕹️ Reglas y controles

- **PC:** flechas o WASD. Espacio o Escape para pausar.
- **Celular:** flechas táctiles o deslizar el dedo sobre el mapa.
- **3 vidas** y **150 segundos**.
- **Punto +10**, **bolita especial +50**, **cereza +100**, **fantasma capturado +200**.
- Cada partida tiene menú, pausa, reinicio, récord, victoria y derrota.

## 🌐 Publicación en GitHub Pages

**Repositorio del proyecto:** [Moreamateo/CogaMan](https://github.com/Moreamateo/CogaMan)  
**Enlace de juego (tras activar Pages):** [https://moreamateo.github.io/CogaMan/](https://moreamateo.github.io/CogaMan/)

1. Creá un repositorio (o usá uno existente para el TP).
2. Subí `index.html` y este `README.md` a la raíz de la rama principal.
3. Abrí **Settings → Pages → Build and deployment** y elegí **Deploy from a branch**.
4. Seleccioná `main` y `/ (root)`, guardá y abrí el enlace publicado.

El archivo HTML ya incluye las imágenes como recursos embebidos; no hace falta subir los PNG por separado.

## 👨‍💻 Créditos

**Hecho con ChatGPT (GPT-6) por Nicolas Barrales, Santiago Orlando y Morea Mateo — 6to 3ra.**
