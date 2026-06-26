# Examen-Pensamiento-computacional
# 🌊 Sistema visual generativo e interactivo — Burbujas en el mar y foca interactiva
*Autora: Camila Romo*

Link al p5js: https://editor.p5js.org/camila.romo/sketches/YP5Qvu4Vt
---

<img width="746" height="742" alt="image" src="https://github.com/user-attachments/assets/91941102-177b-485f-84b1-9d71ab249fe7" />

---
##  Descripción del proyecto
*Burbujas en el Mar* quise basar mi examen en la solemne 2, con el sistema de orbitas flotanto pero cambiando detalles, por ejemplo ahora son burbujas. es un sistema visual generativo e interactivo desarrollado en p5.js, en donde el usuario controla en tiempo real la cantidad y el tamaño de burbujas que ascienden por un fondo marino animado, mientras mueve una imagen de foca a través del espacio usando el teclado. El sistema responde continuamente al mouse y a teclas.

---
##  Sistema de uso
> **Estado**  /  **como se activa**  /  **que muestra**
>
> `Inicio` / Estado inicial al cargar / Título, instrucciones de uso
>
> `interaccion` / `ESPACIO` desde inicio / Fondo marino + burbujas reactivas + foca móvil
>
> `Cierre` / `ENTER` desde interacción / Burbujas lentas + mensaje de cierre

 ---
 ## Inputs (entradas)
 **Input** /  **Acción**
>Movimiento del mouse (X)  /  Controla la cantidad de burbujas (8 – 30)
>
>Movimiento del mouse ( Y)  /  Controla el tamaño de las burbujas (10 – 55 px)
>
>Teclas `←` `→` `↑` `↓`  /  Mueven la foca por el canvas
>
>Tecla `S`  /  Activa la paleta zona media (azules claros)
>
>Tecla `D`  /  Activa la paleta profundidad (azules oscuros)
>
>`ESPACIO`  /  Transición inicio → interacción / cierre → inicio
>
>`ENTER`  /  Transición interacción → cierre

## Procesos principales
>`fondoMar()` — Genera un degradado vertical mediante 20 franjas rectangulares con `lerpColor()`, simulando la profundidad del océano
>
>`dibujarBurbuja(x, y, tamano, i, cantidad)` — Dibuja una burbuja con contorno translúcido, relleno suave y una estela de micro-burbujas debajo mediante un bucle anidado
>
>`moverFoca()` — Lee el estado de las teclas de flecha con `keyIsDown()` y actualiza la posición de la foca, limitando su movimiento con `constrain()`
>
>`dibujarFoca(x, y, radio)` — Renderiza la imagen `foca.png` centrada en la posición actual de la foca usando `imageMode(CENTER)`
>

# Recursos utilizados

>**Variables propias** — `paleta`, `estado`, `focaX`, `focaY`, `radioFoca`, `cantidad`, `tamano`, entre otras
>
>**Condicionales** — Control de estados `(if/else)`, color de burbuja según paleta, filtro de estela según posición Y
>
>**Funciones propias** — `dibujarInicio()`, `dibujarInteraccion()`, `dibujarCierre()`, `fondoMar()`, `dibujarBurbuja()`,`dibujarFoca()`, `moverFoca()`
>
> **Bucles** — Bucle principal de burbujas `(for i)`, bucle de estela `(for j)`, bucle de degradado `(for i en fondoMar)`
>
>**map()** — Mapeo de mouseX → cantidad de burbujas; mouseY → tamaño; índice `i` → componentes de color
>
> **Input para interactividad** — Mouse, teclado `(keyPressed, keyIsDown)`
>
>**3 estados** — `inicio`, `interaccion`, `cierre`
>
> **Multimedia** — Imagen `foca.png` cargada con `preload()` y renderizada con `image()`
>

Outputs (salidas)
-

>Canvas animado de 600 × 600 px
>
>Burbujas ascendentes con cantidad y tamaño al mouse
>
>foca movible con las flechas del teclado
>
>fondo marino con degradado 
>
>cambio de paleta de colores (zona media / profundidad)
>
>texto informativo en pantallas de inicio y cierre
>
---

# Marco conceptual

*Burbujas en el Mar* para este proyecto tomé como referencia dos trabajos, el primero fue Ponyo de Hayao Miyazaki, porque las escenas bajo el mar tienen una atmósfera muy parecida a la que quería lograr. se ven distintos tonos de azul que se oscurecen con la profundidad, burbujas que suben lentamente y un ambiente tranquilo, por eso usé una paleta de colores que va desde azules claros en la superficie hasta azules muy oscuros en el fondo.

El segundo referente fue Zach Lieberman, un artista que crea obras interactivas usando programación, me gustó la forma en que hace que figuras simples, como círculos y las formas transparentes, se muevan y cambien siguiendo reglas del código. En mi proyecto pasa algo parecido, las burbujas se generan y se mueven gracias al programa, y el usuario puede interactuar con ellas moviendo el mouse. La idea no es solo que la persona vea la animación, sino que también pueda formar parte de la experiencia y cambiar lo que ocurre en la pantalla.




# Registro visual del proceso
 *Fondo marino*
 <img width="743" height="742" alt="Captura de pantalla 2026-06-26 042945" src="https://github.com/user-attachments/assets/e9c40d1c-32bd-46ec-89de-53d387a6f116" />

 ---
*Prueba de burbujas*
<img width="642" height="537" alt="Captura de pantalla 2026-06-26 043157" src="https://github.com/user-attachments/assets/26663646-32c7-4470-b718-8f6b420efa86" />

 ---
*Mas burbujas* 
<img width="592" height="643" alt="Captura de pantalla 2026-06-26 044104" src="https://github.com/user-attachments/assets/4c3bc855-f1a4-40fd-953e-d11cda6c3c24" />

 ---
*Foca elegida, llamada Mamegoru*
<img width="260" height="150" alt="Captura de pantalla 2026-06-25 222553" src="https://github.com/user-attachments/assets/55aa5bfc-9f55-4db5-b8ca-f5569f5babee" />

 ---

---

# Reflexión final


La decisión más importante fue hacer que las burbujas se movieran de forma ordenada y no al azar, Para eso usé frameCount, ya que así suben de manera más fluida y dan una sensación de calma como si estuvieran bajo el agua. Si hubiera usado random(), el movimiento se vería mucho más desordenado. Aunque eso significó no usar una función pedida en el trabajo, el resultado visual quedó mucho mejor.

La estela de microburbujas la agregué casi al final. Al principio sentía que las burbujas estaban flotando sin relación con el resto de la escena, con ese detalle se integraron mejor y el fondo se ve con más profundidad.

Dificultades

Lo más complicado fue lograr que el espacio entre las burbujas se mantuviera parejo cuando el usuario cambia la cantidad con mouseX como la distancia depende de la cantidad de burbujas, cuando esta cambia muy rápido también cambia el espacio entre ellas y se producen algunos saltos, probé usar lerp() para suavizar ese efecto pero no quedó del todo bien, así que es algo que todavía podría mejorar.

# diagrama de flujo
<img width="2400" height="1560" alt="diagrama_flujo_burbujas_mar" src="https://github.com/user-attachments/assets/df4d46d3-e6db-41c9-b0c0-dcb86e3cf5a1" />


