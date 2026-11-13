# COGA-MAN: Escape de los Profes 🎮

**TP 2: Hacé tu juego** — Prof. Luis Pandiani

**Nombre/s:** [COMPLETAR LOS NOMBRES DEL GRUPO]  
**Grupo:** [COMPLETAR]  
**Curso:** [COMPLETAR]

## Jugar

Abrí `index.html` en un navegador o publicá el repositorio usando **GitHub Pages**.
No requiere instalación, servidor ni otras carpetas: todo está integrado en el mismo archivo HTML.

## IA utilizada

**ChatGPT — GPT-6.**

## Brief (pedido a la IA)

> Queremos crear COGA-MAN, un juego inspirado en Pac-Man con HTML, CSS y JavaScript, todo dentro de un único `index.html` y adaptable a PC y celular. El jugador controla a Coga usando un sprite de cuatro direcciones y cuatro cuadros por dirección. Debe juntar puntos en un laberinto y escapar de Walter, Lucho, Kevin y Silva, que aparecen como fantasmas pixel art, salen por turnos de una casa central y tienen comportamientos diferentes. Incluí túneles laterales que transporten al jugador de un extremo al otro, tres vidas, puntaje visible, récord, un límite de tiempo, cerezas, poderes temporales, sonidos, menú principal, pantalla de instrucciones, pausa, animaciones y pantallas de victoria y derrota. El juego debe ser desafiante pero posible de completar.

## Diseño

COGA-MAN es un juego arcade de laberintos protagonizado por nuestro amigo Coga. El jugador lo mueve por un mapa recogiendo puntos mientras intenta escapar de los profesores Walter, Lucho, Kevin y Silva. Los cuatro enemigos empiezan dentro de una sala central y salen por turnos; cada uno persigue de manera distinta. Coga puede atravesar túneles laterales, conseguir cerezas y activar el modo recreo con bolitas especiales. Comienza con tres vidas y tiene 150 segundos para completar el recorrido. Se gana al juntar todos los puntos y se pierde al quedarse sin vidas o cuando se termina el tiempo.

## Árbol de decisión

```text
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

## ¿Qué corregimos de la IA?

1. **Movimiento trabado:** reemplazamos el movimiento rígido por desplazamiento continuo entre casilleros y animaciones con los 16 cuadros del sprite de Coga.
2. **Laberinto demasiado difícil y luego demasiado fácil:** modificamos el mapa para que haya obstáculos, más cruces, caminos alternativos y todos los puntos sean alcanzables.
3. **Fantasmas sin salida:** agregamos una casa central donde los cuatro profesores esperan y salen por turnos mediante una puerta.
4. **Interfaz muy cargada:** quitamos las explicaciones laterales, agrandamos el tablero y pasamos las instrucciones a un menú separado.
5. **Personalización:** agregamos sprites pixel art de los profesores, incluidos los nuevos de Walter y Kevin, y los efectos de sonido y finales.

## Reglas y controles

- **PC:** flechas o WASD. Espacio o Escape para pausar.
- **Celular:** flechas táctiles o deslizar el dedo sobre el mapa.
- **3 vidas** y **150 segundos**.
- **Punto +10**, **bolita especial +50**, **cereza +100**, **fantasma capturado +200**.
- Cada partida tiene menú, pausa, reinicio, récord, victoria y derrota.

## Publicación en GitHub Pages

1. Creá un repositorio (o usá uno existente para el TP).
2. Subí `index.html` y este `README.md` a la raíz de la rama principal.
3. Abrí **Settings → Pages → Build and deployment** y elegí **Deploy from a branch**.
4. Seleccioná `main` y `/ (root)`, guardá y abrí el enlace publicado.

El archivo HTML ya incluye las imágenes como recursos embebidos; no hace falta subir los PNG por separado.

**Créditos:** Hecho con ChatGPT (GPT-6) por **[NOMBRES DEL GRUPO]**.

> Antes de publicar, asegurate de tener permiso para utilizar las imágenes de las personas representadas.
