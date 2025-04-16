==**Código para generar buffers en la GPU y guardándolo como un identificador:**==
```C++
unsigned int VBO;
glGenBuffers(n, &VBO)
```
Donde,
- n, es el número de buffers que se van a crear
- &VBO, es el identificador del buffer

==**Código para especificar con que buffer se va a trabajar:**==
```C++
glBindBuffer(GL_ARRAY_BUFFER, &VBO)
```
Bind ⇒ Tomar algo y usarlo en el momento
El **primer parámetro** es que tipo de información se va a guardar.
Este pedazo de código nos ayuda a limitar que todo lo que se escriba después de eso se base en el identificador &VBO. <mark style="background: #FFB8EBA6;">Es necesario usarlo para que el compilador sepa con qué buffer se está trabajando en ese momento.</mark>

==**Código que permite copiar de la CPU a la GPU:**==
```C++
glBufferData(GL_ARRAY_BUFFER, sizeof(vertices), vertices, GL_STATIC_DRAW)
```
Donde,
- **Parámetro 1°** ⇒ tipo del buffer
- **Parámetro 2°** ⇒ tamaño de la data (vértices) en bytes, se puede colocar directamente el valor.
- **Parámetro 3°** ⇒ data actual que queramos enviar, de dónde se va a copiar los datos en la CPU hacia un buffer en la GPU (VBO)
- **Parámetro 4°** ⇒ Indicador al compilador de cómo se debe almacenar la información, dependiendo de la información se va a almacenar en una zona de la GPU más cercana.
    - **STREAM**, los datos se definen una vez y se borran
    - **STATIC**, los datos se almacenan, se definen una vez y se usa muchas veces
    - **DINAMIX**, los datos se cambian y se van a usar muchas veces

==**Código para generar el Vertex Shader:**==
```C++
gl_Position = vec4(aPos.x, aPos.y, aPos,z, 1.0)
```
Donde,
- Las primeras líneas se usan para identificar las entradas que se tienen en el GPU Processor
- Todo lo que esté dentro de “void main” es código
- w (parámetro 1.0) nos sirve para la proyección o perspectiva en un futuro.

==**Compilar un código:**==
```C++
const char *vertexShaderSource = "\#version 330 core\n ..."
```
Guardando un código en el espacio de memoria de la CPU

==**Código para crear un Shader Object:**==
```C++
unsigned int vertexShader;
vertexShader = glCreateShader(GL_VERTEX_SHADER);
```

==**Compilar un Shader:**==
```C++
glShaderSource(vertexShader, 1, &vertexShaderSource, NULL);
glCompilerShader(vertexShader)
```
En la primera línea estamos mandando el Shader creado anteriormente hacia la GPU para posteriormente ser compilado.

==**Código Fragment Shader - Color**==
```C++
\#version 330 core
out vec4 FragColor;
void main() {
	FragColor = vec4(1.0f, 0.5f, 0.2f, 1.0f)
}
```

==**Linking Vertex Attributes**==
```JavaScript
glVertexAttribPointer(0, 2, GL_FLOAT, GL_FALSE, 7 * sizeof(GLfloat), (GLvoid*)0)
```
⇒ El **primer parámetro [0]** corresponde a la locación a la que se tiene que ir.
⇒ El **segundo parámetro [2]** corresponde al número de datos que se tienen que ir
⇒ El **tercer parámetro [GL_FLOAT]** corresponde al tipo de dato que se va a enviar
⇒ El **cuarto parámetro [GL_FALSE]** corresponde a si el dato debe ser normalizado o no
⇒ El **quinto parámetro [7 * sizeof(GLfloat)]** representa cada cuando debemos movernos desde un punto para llegar a la otra posición
- **Ejemplo:** ==**x1**==**, y1, z1**, r2, g2, b2, ==**x3**==**, y3, z3,** el valor del quinto valor en este ejemplo sería 6 debido a que es el número de parámetros que debemos saltar para encontrar las coordenadas de posición (x3).
⇒ El **sexto atributo [(GLvoid*)0 * sizeof(GLfloat)]** indica en dónde se encuentra el primer valor de cada parámetro de color, textura o posición
>[!Alert]
>**Vertex Array Object**
Sirve para guardar todas las configuraciones en una sola línea de código

==**Dibujar Triángulo**==
```C++
glUseProgram(shaderProgram);
glBindVertexArray(VAO);
glDrawArrays(GL_TRIANGLES, 0, 3) //Tipo, empieza, cuántos
```
# EBO
```C++
float vertices[] = {
	0.5f, 0.5f, 0.0f,
	...
}
unsigned int indices[] = {
 0, 1, 2
}
```

```C++
unsigned int EBO
glGenBuffers(1, &EBO)
glBindBuffer(GL_ELEMENT_ARRAY_BUFFER, EBO); //Indicar con cuál EBO se está trabajando
glBufferData(GL_ELEMENT_ARRAY_BUFFER, sizeof(indices). GL_STATIC_DRAW) //Copiando los datos desde indices hacia la GPU
glDrawElements(GL_TRIANGLES, 6, GL_UNSIGNED_INT, 0)
```
```C++
glPolygonMode(GL_FRONT_AND_BACK, GL_LINE)
```
# Texturas
```C++
glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_WRAP_S, GL,MIRRORED_REPEAT)
```
Donde,
- El primer parámetro es el tipo de textura que se tiene
- El segundo parámetro es la configuración que se va a dar en el eje y
- El tercer parámetro es la configuración que se va a dar en el eje x
```C++
floatbordercolor(1.0f, 1.0f, 1.0f)
glTexParameteri(GL_TEXTURE_2D, GL_CLAMP_TO_BORDER, GL_CLAMP_TO_BORDER)
```

==**Texture filtering**==
```C++
glTexParameteri(GL_TEXTURE_2D, GL_CLAMP_TO_BORDER, GL_CLAMP_TO_BORDER)
```

==**Mipmaps**==
```C++
glTexParameteri(GL_TEXTURE_2D, GL_TEXTURA_MIN_FILTER, GL_LINEAR_MINMAP_LINEAR)
```
En un filtro de magnificación, no se puede configurar mipmaps

==**Crear y cargar texturas**==
```C++
unsigned char *data = stbi_load("ruta", &width, &height, &nrChannels, 0)
```
Donde
- &nrChannels depende del RGB
    - RGB = 3 = .jpg
    - RGBA= 4 = .png
==**Generar la textura**==
```C++
glTextImage2D(GL_TEXTURE_2D, 0, GL_RGB, width. height, 0, GL_RGB, GL_UNSIGNED_BYTE, data);
glGenerareMipmap(GL_TEXTURE_2D)
```

> Los tres primeros parámetros son de la GPU y los restantes de la CPU

Donde,
- El primer parámetro especifica la textura que se va a usar, es decir, el formato.
- El segundo parámetro es sobre el mipmap, al poner 0, se está diciendo que se va a trabajar con la imagen original.
- El tercer parámetro el formato que queremos guardar la textura.
# Matriz de modelo
```C++
glm::mat4 model = glm::mat4(1.0f);
model = glm::rotate(model, glm::radians(-55.0f), glm::vec3(1.0f, 0.0f, 0.0f));
```
# Matriz de Vista
```C++
glm::mat4 view = glm::mat4(1.0f);
// note that we're translating the scene in the reverse direction of where we want to move
view = glm::translate(view, glm::vec3(0.0f, 0.0f, -3.0f));
```
# Matriz de Proyección
```C++
glm::mat4 projection;
projection = glm::perspective(glm::radians(45.0f), 800.0f / 600.0f, 0.1f, 100.0f);
```