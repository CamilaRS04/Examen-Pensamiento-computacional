# Examen-Pensamiento-computacional
**Nombre del proyecto:** *Sistema visual generativo e interactivo — Órbitas*

*Autora: Camila Romo*


      Continuando con la — SOLEMNE II   →   EXAMEN —  Es un sistema visual generativo hecho en p5.js donde distintos círculos orbitan continuamente desde el centro de la pantalla. El sistema cambia constantemente según la interacción del usuario.

-
**¿Qué es lo que vemos?**
-
Se observan círculos de distintos tamaños girando alrededor del centro del canvas. Algunas órbitas incluyen un halo semitransparente que genera más profundidad visual. El fondo es negro y los colores cambian dependiendo de la tecla seleccionada, en tonos turquesa, verde y rojo oscuro.

**Mis referentes** *(SOLEMNE II + EXAMEN)*
-

*Vera Molnár*  y  *Victor Vasarely*

<img width="1022" height="605" alt="image" src="https://github.com/user-attachments/assets/a7eab250-f701-48ac-9c9f-44b2362d2d25" />



**CONTENIDOS en p5js**
-
→ Uso de `map()`

→ Uso de `push()`

→ Uso de `rotate()`

→ Uso de `ellipse()`

→ Uso de `fill()`

→ Uso de `noStroke()`

→ Uso de `function keyPressed()`

→ Uso de `random()`

→ Uso de `pop()`

*Explicación de los usos*
-
## Código base

```
let paleta = 'turquesa';
 
function setup() {
createCanvas(600, 600);
angleMode(RADIANS);
}
 
function draw() {
background(20);
 
let cantidad = map(mouseX, 0, width, 5, 20);   // número de órbitas
let tamaño   = map(mouseY, 0, height, 10, 80); // tamaño de las formas
 
for (let i = 0; i < cantidad; i++) {
push();
translate(width / 2, height / 2);
rotate(frameCount * 0.01 + i);
 
let radio = 50 + i * 25;
 
dibujarOrbita(i, cantidad, radio, tamaño);
 
pop();
  }
}
```
## ¿Qué hace este codigo?
fnalksnfalkfnaslnfaskfnaskf

## Código que continua

```
let paleta = 'turquesa';
 
function setup() {
createCanvas(600, 600);
angleMode(RADIANS);
}
 
function draw() {
background(20);
 
let cantidad = map(mouseX, 0, width, 5, 20);   // número de órbitas
let tamaño   = map(mouseY, 0, height, 10, 80); // tamaño de las formas
 
for (let i = 0; i < cantidad; i++) {
push();
translate(width / 2, height / 2);
rotate(frameCount * 0.01 + i);
 
let radio = 50 + i * 25;
 
dibujarOrbita(i, cantidad, radio, tamaño);
 
pop();
  }
}
```

## ¿Qué hace este codigo?
fnalksnfalkfnaslnfaskfnaskf
