# Valores, tipos y operadores
### Tipos
- Numéricos
- Cadenas
- Booleanos
- Indefinidos
### Operadores
- Binarios (`+`,`-`, `*`, `/` y `%`)
- Concatenación de cadenas (`+`)
- Comparación (`==`, `!=`, `===`, `!==`, `<`, `>`, `<=`, `>=`)
- Logica (`&&`, `||`, `??`)
- Unarios (`-` para negar un número, `!` para negar lógicamente, y `typeof` para encontrar el tipo de un valor)
- Ternarios (`a ? b : c`)
### Operadores ?? y ||
El operador ```??``` devuelve va a devolver el valor de la derecha solo si el de la izquierda es ```null``` o ```undefined```, no si es algún otro valor que pueda convertirse en false.
El operador ```||``` devolverá el valor de su izquierda cuando ese valor pueda convertirse en true y devolverá el valor de lo derecha en el caso contrario.

>Las reglas para convertir cadenas y números en valores Booleanos establecen que `0`, `NaN` y la cadena vacía (`""`) cuentan como `false`, mientras que todos los demás valores cuentan como `true`.

```Javascript
console.log(0 || 100);
// → 100
console.log(0 ?? 100);
// → 0
console.log(null ?? 100);
// → 100
```

# Estructura del programa
## Expresiones y valores
### Expresiones
Fragmento de código que produce un valor. Una expresión puede contener a otra.
Puede producir cambios secundarios, que es cuando una expresión afecta a declaraciones realizadas después de ella.
> Si una expresión corresponde a un fragmento de oración, una _declaración_ de JavaScript corresponde a una oración completa.

El punto y coma al final de la declaración simboliza el fin de la misma, si no se pone, se tomara a la siguiente línea como parte de la expresión.
### Enlaces o variables
#### let
Indica que esta frase va a definir un enlace
```javascript
let caught = 5 * 5;
```
Una vez definido, también puede ser usado como una expresión
```javascript
let ten = 10;
console.log(ten * ten)
// → 100
```
El operador '=' se puede usar en cualquier momento en enlaces existentes para desconectarlos de su valor actual
``` javascript
let mood = "light";
console.log(mood);
// → light
mood = "dark";
console.log(mood);
// → dark
```

> Los enlaces son como tentáculos en lugar de cajas, no _contienen_ valores; los agarran. Cuando defines un enlace sin darle un valor, el tentáculo no tiene nada que agarrar, obteniendo el valor `undefined`.
#### var
Es la forma en la que se declaraban las variables en JS anterior a 2015.
#### const
Significa constante, define un enlace constante, que apunta al mismo valor mientras exista. Es util para enlaces que solo dan un nombre a un valor para poder referir fácilmente a él más tarde.
```javascript
var name = "Ayda";
const greeting = "Hola ";
console.log(greeting + name);
// → Hola Ayda
```
### Nombre de enlaces
- No puede empezar con un número
- Puede incluir signos de `$` o `_` pero no otros signos de puntuación o caracteres especiales
- No se deben usar palabras clave
- Se sigue upperCase
### Entorno
Colección de enlaces y valores que existen en un momento dado. Cuando un programa se inicia, este entorno no está vacío. Siempre contiene enlaces que forman parte del lenguaje estándar, y la mayoría de las veces también tiene enlaces que proporcionan formas de interactuar con el sistema circundante.
### Funciones
Fragmento de programa envuelto en un valor. Por ejemplo, en un entorno de navegador, el enlace `prompt` contiene una función que muestra un pequeño cuadro de diálogo pidiendo la entrada del usuario. Se utiliza de la siguiente manera:
```javascript
prompt("Enter passcode")
```
### Control de flujo
Cuando tu programa contiene más de una sentencia, las sentencias se ejecutan como si fueran una historia, de arriba hacia abajo. Por ejemplo, el siguiente programa tiene dos sentencias. La primera le pide al usuario un número, y la segunda, que se ejecuta después de la primera, muestra el cuadrado de ese número:
```javascript
let elNumero = Number(prompt("Elige un número"));
console.log("Tu número es la raíz cuadrada de " + elNumero * elNumero);
```
La función `Number()` convierte un valor a un número
### Ejecución condicional
La ejecución condicional se crea con la palabra clave `if` en JavaScript. En el caso simple, queremos que cierto código se ejecute si, y solo si, una cierta condición es verdadera.
![[Pasted image 20250218100541.png]]
```javascript
let elNumero = Number(prompt("Elige un número"));
if (!Number.isNaN(elNumero)) {
  console.log("Tu número es la raíz cuadrada de " +
              elNumero * elNumero);
}
```
La palabra clave `if` ejecuta o salta una sentencia dependiendo del valor de una expresión booleana.
La sentencia después del `if` está envuelta entre llaves (`{` y `}`) en este ejemplo. Las llaves se pueden usar para agrupar cualquier cantidad de sentencias en una sola sentencia, llamada un _bloque_.
Se pueden "encadenar" múltiples pares `if/else`
```javascript
let num = Number(prompt("Escoge un número"));

if (num < 10) {
  console.log("Pequeño");
} else if (num < 100) {
  console.log("Mediano");
} else {
  console.log("Grande");
}
```
### Bucle while y do
![[Pasted image 20250218100553.png]]
El control de flujo mediante bucles nos permite regresar a algún punto en el programa donde estábamos antes y repetirlo con nuestro estado de programa actual.
```javascript
let numero = 0;
while (numero <= 12) {
  console.log(numero);
  numero = numero + 2;
}
// → 0
// → 2
//   … etcétera
```
> JavaScript también tiene un operador para la potencia `(2 ** 10)`

Un bucle `do` es una estructura de control similar a un bucle `while`. La única diferencia radica en que un bucle `do` siempre ejecuta su cuerpo al menos una vez, y comienza a probar si debe detenerse solo después de esa primera ejecución.
```javascript
let tuNombre;
do {
  tuNombre = prompt("¿Quién eres?");
} while (!tuNombre);
console.log("Hola " + tuNombre);
```
### Bucles for
```javascript
for (let numero = 0; numero <= 12; numero += 2) {
  console.log(numero);
}
// → 0
// → 2
//   … etcétera
```
Los paréntesis después de la palabra clave `for` deben contener dos punto y coma. La parte antes del primer punto y coma _inicializa_ el bucle, generalmente definiendo una variable. La segunda parte es la expresión que _verifica_ si el bucle debe continuar. La parte final _actualiza_ el estado del bucle después de cada iteración. En la mayoría de los casos, esto es más corto y claro que un `while` tradicional.
### Switch
JavaScript hereda la estructura de C/Java:
```javascript
switch (prompt("¿Cómo está el clima?")) {
  case "lluvioso":
    console.log("Recuerda llevar un paraguas.");
    break;
  case "soleado":
    console.log("Vístete ligero.");
  case "nublado":
    console.log("Sal al exterior.");
    break;
  default:
    console.log("¡Tipo de clima desconocido!");
    break;
}
```
### Comentario
Se usa `//` para líneas y `/* */` para fragmentos
# Funciones
## Definir una función
Comienza con la palabra clave `function` y en sus paréntesis van los _parámetros_ (de 0 a n) que van a ser usados y el _cuerpo_ de la función envuelto entre `{}`
```js
const square = function(x) {
  return x * x;
};
// Llamado
square(12);    // → 144
```
Una instrucción `return` determina el valor que devuelve la función. Cuando el control llega a una instrucción de ese tipo, salta inmediatamente fuera de la función actual y le da el valor devuelto al código que llamó a la función.
## Enlaces y ámbitos
Cada enlace tiene un _ámbito_, que es la parte del programa en la que el enlace es visible.
### Enlaces locales
Enlaces creados para los parámetros de una función o declarados dentro de una función que solo pueden ser referenciados dentro de la misma.
Los enlaces declarados con `let` y `const` en realidad son locales al _bloque_ en el que se declaran, por lo que si creas uno de ellos dentro de un bucle, el código antes y después del bucle no puede “verlo”.
> Los enlaces creados con la palabra clave `var`, son visibles en toda función en la que aparecen o en todo el ámbito global, si no están dentro de una función.

```js
let x = 10;   // global
if (true) {
  let y = 20; // local al bloque
  var z = 30; // también global
}
```
### Ámbito anidado
```js
const hummus = function(factor) {
  const ingredient = function(amount, unit, name) {
    let ingredientAmount = amount * factor;
    if (ingredientAmount > 1) {
      unit += "s";
    }
    console.log(`${ingredientAmount} ${unit} ${name}`);
  };
  ingredient(1, "lata", "garbanzos");
  ingredient(0.25, "taza", "tahini");
  ingredient(0.25, "taza", "jugo de limón");
  ingredient(1, "diente", "ajo");
  ingredient(2, "cucharada", "aceite de oliva");
  ingredient(0.5, "cucharadita", "comino");
};
```
El código dentro de la función `ingredient` puede ver el enlace `factor` de la función exterior, pero sus enlaces locales, como `unit` o `ingredientAmount`, no son visibles en la función exterior.
El conjunto de enlaces visibles dentro de un bloque está determinado por el lugar de ese bloque en el texto del programa. Cada bloque local también puede ver todos los bloques locales que lo contienen, y todos los bloques pueden ver el bloque global. Este enfoque de visibilidad de enlaces se llama _ámbito léxico_.
### Funciones como valores
```js
let launchMissiles = function() {
  missileSystem.launch("now");
};
if (safeMode) {
  launchMissiles = function() {/* no hacer nada */};
}
```
### Función declarativa
```js
function square(x) {
	return x * x;
}
```
Una función declarativa NO forma parte del flujo de control regular de arriba hacia abajo. Se mueven al principio de su alcance y pueden ser utilizadas por todo el código en ese alcance.
### Función flecha
```js
const roundTo = (n, step) => {
  let remainder = n % step;
  return n - remainder + (remainder < step / 2 ? 0 : step);
};
```
> Expresa algo así como “esta entrada (los parámetros) produce este resultado (el cuerpo)”.

