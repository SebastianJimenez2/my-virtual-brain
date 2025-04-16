![[Untitled.png]]
**Computación Gráfica**. Manipulación, creación y almacenamientos de modelos e imágenes. Es también una forma eficiente de transmitir información.
**Computación Gráfica Interactiva.** La manipulación de gráficos es realizada en tiempo real usando controles para que los mismos sean manipulados por el usuario. Se necesita **indispensablemente** un sistema gráfico interactivo, un sistema de entrada, procesamiento y salida. El **primer modelo** de este tipo nace en 1963 (sketchpad)
**Batch Computer Graphics.** No es en tiempo real, para observar un resultado tuvo que haber un procesamiento previo. Se podría considerar el término batch como “renderizando fuera de línea”.
- Batch es lo contrario a tiempo real (300 - 500 milisegundos).
## Aplicaciones de la computación gráfica
- Películas, con manipulación de gráficos
- Videojuegos
- Simulaciones, en dónde se ahorran recursos en la vida real, además de entrenar personal en manipulación de dispositivos peligrosos.
- CAD-CAM (Computer-Aided Design - Computer-Aided Manufacturing) ⇒ Diseño asistido por computadora - fabricación asistida por computadora
- Arquitectura, reproducción de una casa para crear cimientos antes de construirse, además se puede simular la iluminación dentro de un lugar (usando algoritmos de iluminación global)
- Realidad virtual y aumentada
- Visualización Científica
- Imágenes Médicas
## Arquitectura básica “Framework”
Como principio tenemos HW, generalmente son tres tipos de dispositivos:
- Entrada de información
- Salida de información
- GPU (unidad de procesamiento de gráficos) ⇒ Sistema Gráfico
En la parte de software encontramos:
- El primer nivel, lo más cercano al HW, la librería de gráficos que básicamente cumple la función de prestar funciones que cuando son compiladas y es enviada al HW este puede entender.
- Aplicación, es más cerca al usuario.
- Base de datos o modelo de aplicaciones, son comúnmente reutilizados para optimizar tiempo.
## Enabling Computer Graphics
**Revolución en el HW.** Nos podemos fundamentar en la ley de Moore que dice que cada 12-18 meses, un computador mejora con un factor de 2 en precio.
Las **GPU** son usadas específicamente para trabajar con gráficos, lo que quiere decir, que usan operaciones matemáticas simples, por ejemplo: multiplicación de matrices.
**GPGPU ⇒ "Cómputo de Propósito General en Unidades de Procesamiento Gráfico".** Se refiere al uso de una GPU (unidad de procesamiento gráfico) para realizar tareas de cómputo científico y de ingeniería de propósito general, además de su uso tradicional para renderizado de gráficos.
**Mejoras en Software**
- Algoritmos y estructura de datos
- Paralelismo, se pueden tener varios procesadores trabajando al mismo tiempo, pero de manera conjunta en una misma tarea para sumar el procesamiento computacional.
**Cloud Computing.** Conectarse mediante la red no en un punto similar específicamente y trabajar de manera óptima de todas formas.
## Evolución del Ambiente
1. **Display’s**. Generaban líneas en lugar de caracteres
2. **Display’s de mapa de bits**. Se tienen un conjunto de puntos junto a una matriz de puntos, denominados como pixeles en dónde se encuentra representado un color, los primeros monitores representaban de 16 - 200 colores.
    1. Interacciones mediante WIMP (ventanas, íconos, menús y punteros)
3. **3D Graphics Worstations.** Su precio era demasiado elevado por lo que las personas no lo usaban en sí, y esto evolucionó en un HW monótono, con la diferencia de que si alguien se necesita especializar en gráficos debe disponer de una GPU.
4. **GPU.** Es lo que tenemos en la actualidad.
## Display de Gráficos
Dos tipos de tecnologías:
1. **Tipo Vector.** Se genera el modelo o gráfico mediante suma de vectores, como usando un plano cartesiano y estableciendo las líneas mediante puntos. Se sigue usando hoy en día y es conocido como SVG. Se ha reducido su uso, pero no ha muerto.
2. **Tipo Raster.** Trabaja mediante una matriz de puntos (píxeles). Y básicamente se decide por cada pixel que se va a mostrar o no y si se muestra y es a color, se manda dicha señal.
## Librerias
Actúan como intermediario entre aplicación y HW. Se pueden encontrar de manera privada o libres. OpenGL es la base de todas las demás existentes.
Todas las librerías:
- Son primitivas
- Poseen atributos, luces y transformaciones
- Tienen dos modos:
    - ==**Immediate mode.**== No tiene memoria, lo que se dibuja en una trama se borra inmediatamente, no almacena nada. Cada frame es algo nuevo, tiene que generar todo desde 0 para cada frame.
        - Es una API procedural
        - Mayor flexibilidad para programar.
    - ==**Retained mode.**== Tiene memoria y mantiene la escena que se muestra en pantalla, lo generado lo almacena de tal manera que a la siguiente trama se muestra las diferencias con la anterior presentada.
        - Es una API declarativa
        - Es más fácil de programar debido a que la librería ya trae la mayoría del trabajo hecho, sin embargo, no existe flexibilidad debido a que nos tenemos que adaptar a lo que nos provee la librería.
## Tipos de aplicaciones de gráficos
- **Gráficos basados en muestras.**
    - El procesamiento es más sencillo, sin embargo, no existe más información que solo píxeles.
    - Se toma una muestra del mundo real por medio de una imagen digitalizada o cámara para luego procesarla. Se trabaja directamente con pixeles.
        - **Pixeles**. Son puntos que tienen valores de color.
    - Las muestras se pueden tomar desde cámara, pero no es la única forma, también se puede extraer de sensores de calor
    - Con las muestras capturadas se puede:
        - **Edición de imágenes.** Cambios realizados por el usuario.
        - **Procesamiento de imágenes.** Son operaciones algorítmicas ejecutadas sobre la imagen siendo el computador las que le ejecutan.
- **Gráficos basados en geometría.**
    - No se trabajan con pixeles ya que estos aparecen al final. En este caso la **unidad de medida** son los objetos o modelos. Se va armando al objeto por medio de líneas.
    - Antes el procesamiento de la imagen se realizaba por cuadrados, pero se ha actualizado y ahora son **triángulos.**
    - La unidad más pequeña de medida es primitiva.
    - Los objetos son modelados, no son extraídos de la vida real.
    - Los modelos están formados por primitivas
    - **Modelo.** Es una entidad y pueden tener atributos de iluminación, escalabilidad para luego ser transformado en pixeles.
        - Las primitivas son los ladrillos
        - Varias primitivas es un modelo
        - Cuando unimos modelos con mismos atributos se denomina escena.
    - Una de las **ventajas** es que nosotros podemos ubicar la cámara en dónde queramos. Al momento de tomar la fotografía el modelo se transforma en píxeles. El proceso mencionado previamente se denomina como ==**rendering.**==
    - Se ejecutan **tres principales transformaciones**: translate, sacale y rotate
    - Al momento en que se renderiza se le pueden aplicar los atributos que va a tener el modelo como: iluminación, material, etc.
    - El proceso de renderizado depende de la GPU.
- **Descomposición de un modelo geométrico.** Se pueden dividir modelos más complejos en modelos más simples.
- **Composición de un modelo geométrico.** Unir modelos simples en uno complejo.
# CONCEPTOS BÁSICOS DE REPRESENTACIÓN BÁSICA
- ==**Imaging**== ⇒ Representaciones en 2D
    - **¿Qué es una imagen?** Es un array de dos dimensiones de píxeles.
    - **¿Qué es un pixel?** Es una función que depende de la posición. Todos los pixeles que estén en diferentes posiciones son diferentes ⇒ Píxeles(x, y)
    - **Función Plenóptica (7D).** Permite describir la radiación que llega a la cámara, es dependiente de:
        - La posición del objeto o la cámara.
        - La dirección.
        - Tiempo.
        - Frecuencia, es decir, la radiación.
    - **¿Por qué RGB?** Porque los tres colores ahí son los más sensibles a la cornea humana.
- ==**Modeling**== ⇒ Objetos en 3D
- ==**Rendering**== ⇒ Construir imágenes de 2D en 3D, convertir en pixeles
- ==**Animation**== ⇒ Simular cambios a lo largo del **tiempo**
---
# INTRODUCCIÓN A LA PROGRAMACIÓN DE GRÁFICOS
## **OpenGL**
- Sencilla de utilizar
- No está tan alejada del HW, por lo que su rendimiento es demasiado bueno
- Está enfocado en procesos de rendering.
- No necesita de un sistema de ventanas ni de un sistema de manejo de entradas y salidas
## **Características de OpenGL**
- **Principio de Pipeline.**
    - Pipeline es una cadena de producción, es decir, un proceso que una vez que inicia no tiene retorno.
- **Shaders**. Son espacios en dónde se pueden crear aplicaciones, nosotros lo configuramos y adaptamos.
- Vertex Shading y Fragment Shading se **ejecutan** en la GPU
- **Geometry Shader.** Todo lo que se puede hacer en esta parte, se lo puede hacer en el vertex shading, por lo que su uso puede ser opcional
# Coordinadas Baricéntricas
Centro de un triángulo, es importan debido a que nos va a ayudar a hacer operaciones con nuestras primitivas.
![[Untitled 1.png]]
Donde:
- a: es la línea base de un triángulo hasta la intersección en el centro
- a’: es la línea entre la punta de un triángulo hasta la base
Además, ==**alfa + beta + gamma debe ser igual a 1.**==
Los valores de alfa, beta y gamma nos permiten ubicarnos dentro del triángulo y saber dónde estamos trabajando.
Alfa es más grande cuando se acerca más a $P_0$
**Para el deber:** Colocar un punto en cualquier lado del triángulo y mediante este encontrar alfa, beta y gamma.
# Arquitectura de un Computador
**Lógica de programación en el CPU**
LA GPU no es independiente, siempre está controlada por la CPU, entonces cualquier cosa programada se hace en la CPU, sin embargo, una parte de la programación va a ser enviada a la GPU. Esto se realiza mediante la herramienta OpenGL.
La aplicación y la compilación son parte de la **CPU** ⇒ **secuencial**
La geometría, rasterización, fragmentos y pantalla es parte de la **GPU** ⇒ **paralelo**
- ==**Shader**==. Una aplicación que se ejecuta en la GPU.
## **Graphics Pipeline**
- **Aplicación**
- **Command:** Es el compilador, se transforma en un conjunto de comandos, parte de estos comandos se envían a la tarjeta gráfica
- **Geometry:** Tareas de la GPU: transformaciones de vertex, iluminación, ensamblaje de primitivas
- **Rastering:** Convertir triángulos a fragmentes, interpolación de coordenadas, interpolación de color
- **Fragment:** Quiere decir los cálculos de profundidad, mezcla de colores, gestión de texturas
- **Display:** Es lo que se observa en el computador
## **Programming Pipeline**
- **Entrada de información.** Siempre van a ser vértices, un modelo se empieza con vértices. Estos vértices se trabajan en tres coordenadas **(x, y, z) ⇒ de tipo flotante (32 bits - 4 bytes)**, pero no implica que no se pueda hacer en **2D**, para este proceso **z=0.**
- **Transformaciones.** Permite hacer transformaciones, tales como: rotación, escala y traslación.
- **Clipper**. Es un proceso de optimización que consiste en trabajar con los vértices que se van a observar en pantalla, en otras palabras, descartar los vértices que no se van a observar en pantalla. Es un **proceso automático** de la librería.
- **Proyección.** También conocido como perspectiva. Entra en juego la **profundidad**, básicamente es hacer que los objetos que estén **más cerca** del observador se vean **más grandes** y los objetos **más lejanos más pequeños.**
- **Rastering.** Es diferente al proceso de rendering. Consiste en la conversión de un triángulo (primitiva) en pequeñas **cajitas (denominadas como fragmentos)** que **todavía no tienen color.** El proceso de dar color a los fragmentos se denomina como **rendering.**
- **Pixeles**. Fragmentos con color que van a ser impresos en el monitor.
# OpenGL

> [!important] VBO significa "Vertex Buffer Object" y es un objeto que se utiliza para almacenar datos de vértices en la memoria de la GPU. Almacenar los vértices en la GPU permite un mayor rendimiento y una mayor velocidad de procesamiento de gráficos. Los VBO se utilizan comúnmente en aplicaciones de gráficos 3D para almacenar información de vértices como posiciones, colores, texturas, normales y otros atributos.

Usa el modo de gráficos Inmmedite. Es multiplataforma y se basa en lenguaje C y en ciertas cosas del lenguaje C++.
Nos permite adaptar HW programable.
==**Shader**== ⇒ Aplicaciones dentro de la GPU
## Shaders
- No se utilizan datos de entrada como en aplicaciones tradicionales, este tiene dos nombres para tipos de datos de entrada:
    - Atributos
    - Uniforms
## Representing Shapes
OpenGL usa triángulos, y con la unión de estos, se pueden lograr diferentes figuras, organizando las primitivas de manera adecuada.
La cantidad de primitivas permite dar la forma de cierta figuras o superficies
## Sistema de Coordenadas
- **Coordenadas cartesianas**, utiliza tres coordenadas (x, y z) los puntos siempre se deben encontrar en ==**punto flotante (32 bits para guardar información)**== se usa para trabajar con los ==**modelos.**==
- **Coordenadas físicas (display),** utiliza la escala (x, y) ya no se trabajan con escalas flotantes, sino con enteros, y cada punto establecido aquí se puede denominar como pixel.
    - **==El rendering y la escala es dependiente del display.==**
- El área visible está definida por las coordenadas que se encuentren dentro del **rango [-1, 1]**
- Es recomendable que cada modelo sea creado en base a su propio sistema de coordenada.
- Para pasar de un sistema local a uno global se usan transformaciones: rotación, escala y traslación.
---
Todo lo que son vértices se trabaja en un solo array.
NDC ⇒ Coordenadas normalizadas, puntos que estén dentro del rango [-1, 1]
La memoria de la GPU se organiza por **objetos,** por lo que si se desea guardar información en la memoria de la GPU se debe usar buffer objects, que no tienen una dirección como tal, sino un identificador (en donde se encontrará almacenada la información).
Shader Program Object es donde se guarda el código dentro de la GPU
Shader Objects se guardan atributos y uniforms codigo del vertex shader y codigo del fragment shader, en otras palabras, se guardan instrucciones.
Si no se mueve los atributos de la CPU como objetos a la GPU, no vamos a poder usar dichos elementos.
Cuando la información que se guarda como
- Vertex Buffer Object en la GPU se están almacenando como vértices en la CPU, pueden almacenarse muchos vértices en el VBO
>[!Info] 
>Ver más detalle en [[Código]]
## Fragment Shader - Color
RGBA ⇒ Red, Green, Blue, Alpha (opacidad), estos datos se deben normalizar y van en el rango [0, 1]
Si alfa es uno, deja pasar los colores, si es cero, no lo deja.
En los VBO’s podemos almacenar no solo posiciones, sino también colores, con el fin de mejorar el rendimiento de nuestro programa. Es necesario definir dentro de la función creada, que clase de atributos se están enviando, asignando un nombre y una locación.
# OBJETOS GEOMÉTRICOS Y TRANSFORMACIONES
Indexación. No guardar vértices similares, sino que solo se guarda una sola vez
**Element Buffer Object (EBO).** Guardan índices, aquí se dejan de almacenar flotantes, sino que se guardan enteros.
>[!Info]
Ver más en [[Código]]
# Shaders
Se programa en GLSL que es un lenguaje procedural de alto nivel.
**Vertex Processor.**
Opera sobre los valores de los vértices y sus datos asociados. Generalmente realiza:
- Transformaciones de vértices
- Transformación de la normal y normalización
- Generación y transformación de coordenadas de textura
- Iluminación
- Aplicación del color de materiales.
**Fragment Processor**
Su objetivo es encontrar color a los gráficos
- Operaciones en valores interpolados
- Acceso a texturas
- Aplicación de texturas
- Niebla
- Suma de colores
**Descripción Básica del Lenguaje**
- Sampler1D y Sampler2D para texturas 1D y 2D respectivamente
- Calificativos para tipo de entrada y salida
    - **Attribute**. Comunica un valor que cambia frecuentemente, desde la aplicación al vertex shader. Se pueden tener hasta 16 entradas de cuatro componentes c/u.
    - **Uniform**. Comunica un valor que no cambia frecuentemente, desde la aplicación a cualquier shader. Están presentes tanto en el vertex como en el fragment al mismo tiempo. Puede considerarse como una variable global. ==**No hay uniforms de salida**==
    - **Varying**. Comunica un valor interpolado desde el vertex shader al fragmente shader
    - Las **texturas** tienen un **tipo de dato** que se denomina ==**sampler**==, para sacar una textura se puede realizar mediante una fotografía.
# Texturas
Al trabajar con imagen:
- Se tiene un formato en el archivo de la imagen
- Las coordenadas para rellenar una primitiva, no tienen nada que ver con las coordenadas de la imagen.
- Las coordenadas de la imagen se denominan: **coordenadas de textura.**
- Las coordenadas de textura van entre cero y uno. Por lo cual no pueden ser negativas. Cero es la esquina izquierda inferior y uno es la esquina derecha superior.
- Obtener las coordenadas de textura se llama ==**sampling**==.
- Configuraciones para rellenar área indefinida ⇒ ==**Texture Wrapping**==
    - **GL_REPEAT**. Repite la imagen rellenando el área indefinida con la misma imagen
    - **GL_MORRORED_REPEAT**. Repite la imagen como si tuviese un espejo por las áreas a rellenar.
    - **GL_CLAMP_TO_EDGE**. Alarga la textura de la imagen, por sus bordes, rellenando así el área restante.
    - **GL_CLAMP_TO_BORDER.** Deja al usuario rellenar el área vacía con un color específico elegido por el usuario.
>[!Info]
 Ver más en [[Código]]
- Los píxeles del archivo de textura se denominan ==**texel.**==
- **Magnificación (Zoom In)**: Cuando tenemos un texel pequeño que se divide en varios pixeles
- **Minificación**: Muchos texeles se reducen a un pixel pequeño
# Algoritmos de minificación y magnificación
- **GL_NEAREST** ⇒ Método default de filtrado en OpenGL. Toma el texel que se encuentra más cerca y los demás son eliminados.
- **GL_LINEAR** ⇒ Ejecuta un algoritmo que se denomina interpolación bilineal. Se van sumando las distancias y en función de la distancia se mezclan los texeles. Produce un efecto más suave en la imagen, pero los pixeles individuales son menos visibles.
>[!Info]
 Ver más en [[Código]]
- **Texel Swimming.** Mientras más lejos el pixel está, más sampleado se vuelve. Solo existe en minificación.
- **Vertex Shader** ⇒ El tipo de dato que se usa en un uniform de textura es la palabra reservada ‘sampler2D’
- **Función texture()** ⇒ Se encarga de recibir la imagen**:**
    - Primer parámetro, datos de los texeles (imagen)
    - Segundo parámetro, coordenadas de textura
# Texturas Pt. 2
**Texture Unit** ⇒ Es el identificativo de una textura para poder usar varias texturas al mismo tiempo
Una primitiva puede tener 16 texturas, la escena completa no se ve involucrada por este valor.
```C++
glActiveTexture(GL_TEXTURE0) // Nos dice que GL_TEXTURE0 es la textura 0
glBindTexture(TEXTURE_2D, <texture>) // Lo que se encontraba en la GPU va con el texture indicado 
```
# Transformaciones Geométricas
Para las transformaciones se debe usar una matriz identidad 4x4
Operación de **escala NO uniforme** ⇒ cambia la dirección del vector, se cambia, se altera en cuanto a proporciones.
Operación de **escala uniforme** ⇒ no cambia la dirección del vector, solo se incrementa. ==Mantiene la proporción del objeto.==
**Matriz de transformación** ⇒ Es una matriz (4x4) identidad en donde los valores que deberían ser 1 son reemplazados por los valores (x, y, z, 1) diagonalmente, respectivamente.
$$\begin{equation}  
\begin{pmatrix}  
S_x & 0 & 0 & 0 \\  
0 & S_y & 0 & 0 \\  
0 & 0 & S_z & 0 \\  
0 & 0 & 0 & 1 \\  
\end{pmatrix}  
\end{equation}$$
**Matriz de traslación.** Nos permite mover la figura de un punto a otro dentro del mapa.
$$\begin{equation}  
\begin{pmatrix}  
1 & 0 & 0 & T_x \\  
0 & 1 & 0 & T_y \\  
0 & 0 & 1 & T_z \\  
0 & 0 & 0 & 1 \\  
\end{pmatrix}  
\end{equation}$$
Si no se puede trasladar, quiere decir que se está trabajando con un vector dirección, es decir, cuando se trabaja con vectores de dirección, no importa la posición porque la dirección siempre va a ser la misma.
**Rotación.** Para hacer el movimiento de rotación, se necesita:
- Cuánto debe rotar, es decir, el ángulo de rotación
- Eje de rotación, si gira respecto x, y o z.
**Matriz de rotación en X (Pitch)**
$$\begin{equation}  
\begin{pmatrix}  
1 & 0 & 0 & 0 \\  
0 & cos\theta & -sen\theta & 0 \\  
0 & sen\theta & cos\theta & 0 \\  
0 & 0 & 0 & 1 \\  
\end{pmatrix}  
\end{equation}$$
**Matriz de rotación en Y (Yaw, Heading)**
$$\begin{equation}  
\begin{pmatrix}  
cos\theta & 0 & sen\theta & 0 \\  
0 & 1 & 0 & 0 \\  
-sen\theta & 0 & cos\theta & 0 \\  
0 & 0 & 0 & 1 \\  
\end{pmatrix}  
\end{equation}$$
**Matriz de rotación en Z (Roll)**
$$\begin{equation}  
\begin{pmatrix}  
cos\theta & -sen\theta & 0 & 0 \\  
sen\theta & cos\theta & 0 & 0 \\  
0 & 0 & 1 & 0 \\  
0 & 0 & 0 & 1 \\  
\end{pmatrix}  
\end{equation}$$
# Sistemas de Coordenadas en 3D
Existen 5:
- Espacio local
    - Matriz de transformación global
- Espacio glocal
    - Matriz de vista
- Espacio de vista
    - Matriz de Proyección
- Espacio Clip
    - Automático
- Espacio de pantalla
Para cambiarse de un sistema a otro se usa una matriz de coordenadas
## Espacio Local
Es un sistema de coordenadas en forma local, es decir, cada objeto presenta un eje de coordenadas propio.
## Espacio Global
Los objetos dentro de la vista comparten el mismo sistema de coordenadas.
Aquí se crea un nuevo elemento, la cámara.
## Espacio de Vista
Todos los objetos van a estar referenciados a un sistema de coordenada cuyo eje se encuentra en la cámara, es decir, cada modelo va a estar en el eje respecto a la cámara.
## Espacio de Clip
Tomar todo lo visible y todo lo que está fuera de ese rango es recortado.
Se toma todo el área visible de la cámara se va a transformar entre coordenadas entre [-1; 1], todo los demás estarán fuera de estas coordenadas y por lo tanto se van a descartar.
Es en este caso aparecen dos planos:
- Near plane
- Far plane
Todo lo que esté fuera de estos planos son descartados, de manera completa o parcial.
![[Untitled 2.png]]
En esta ocasión, se debe tener en cuenta que los objetos más cercanos al near space se deben ver más grande y los mas cercanos al plano lejano se deben ver más pequeños, todo este proceso se realiza dentro del vertex shader.

> (x, y, z, w) ⇒ w ⇒ distancia de la cámara

Entre mayor sea W los objetos son más separados entre sí.
- **Proyección Ortográfica.** Define un espacio de tipo Q, el ==**plano cercano es idéntico al plano lejano.**== En este caso ==**w es igual a 1 para todos los objetos.**== Se necesita definir la distancia entre el plano lejano y el plano lejano y el tamaño de los planos.
```C++
glm::ortho(GLint left, GLint right, GLint bottom, GLint top, GLfloat neat, GLfloat far)
```
![[Untitled 3.png]]
- **Proyección de Perspectiva.** Los objetos más cercanos se ven más grandes y los más lejanos se ven más pequeños. ==**Los objetos ya tienen valores diferentes en w.**== El truco es dividir las coordenadas para w. El plano cercano es más pequeño que el plano lejano.
```C++
glm::perspective(GLfloat FoV, GLfloar aspect, GLfloat near, GLfloat far)
```
![[Untitled 4.png]]
- **FoV** ⇒ Comúnmente seteado en 45
- **Aspect** ⇒ widht / height
- **Near and far** ⇒ [0.1, 100.0]