# ¿Qué es Vue?
Es un framework de [[JavaScript]] que hace a la construcción interactiva y reactiva para el frontend de una aplicación web.
>[!Note]
>Un framework es una librería de un tercero que proporciona funcionalidad y un conjunto de reglas. Además al ser reactivo permite al usuario actualizar la pantalla de manea dinámica.

Ningún framework como Vue es necesario, sin embargo, al usarlo:
- No reinventamos la rueda
- Podríamos escribir código no óptimo
- Trabajar más duro
## Diferentes formas de usar Vue
- Controlar partes de páginas HTML o de páginas enteras.
- Controlar el frontend completo de una aplicación web. 
>[!Note]
>SPA => el servidor solo manda una página HTML, de este modo, Vue controla todo el UI.
# Crear aplicaciones Vue
Para crear una aplicación de Vue se debe seguir la siguiente sintaxis dentro de aun archivo `.js`:
```JavaScript
const app = Vue.createApp({
  data() {
    return {
		// Valores que se va a devolver o se van a usar en un archivo html
    };

  },

  ... other options

});

app.mount('#parte-que-se-va-a-acceder-con-Vue(ID)');
```
Luego, en el archivo `.html` se debe:
```JavaScript
// Definir a Vue
<script src="https://unpkg.com/vue@3.4.9/dist/vue.global.js" defer></script>

// Con eso se podrá usar todas las funciones y funcionalidades de Vue.
```
# Manipular datos
## Datos e interpolación
Es el control de la app de Vue al código HTML, se logra usando doble corchetes `{{ ... }}` en HTML apuntando a la variable que se creó en la aplicación de Vue.
## v-bind `:`
Se usa para asignar datos en nuestra aplicación de Vue a etiquetas HTML.
## v-html
Sirve para pasar datos con etiquetas html de una aplicación Vue a un archivo `.html`.
## v-on `@`
Es para escuchar eventos, es decir, para definir qué pasa cuando se ejecuta una acción en específico.
## v-once
Hace que un evento dinámico solo cambie una vez, luego se mantendrá en un estado de "bloqueo".
## v-model
Es una forma de resumir la existencia de v-bind y v-on en un solo. A esto se le conoce como two-way binding, ya que se comunica en dos direcciones.
## Conditional content
### v-if (and v-show)
Permite renderizar un contenido en específico si y solo si se cumple cierta condición. También se puede combinar con v-else o incluso con v-else-if
### v-for
Puede ser usado para renderizar multiples elementos dinámicamente, por lo que, se puede usar en conjunto con arreglos, objetos o rangos.
También existen variaciones en dónde se pueden extraer valores, valores e **índices**, **llaves** e índices.
>[!Note]
>Vue re-usa los elementos del DOM para optimizar el rendimiento de las páginas, lo que puede llevar a bugs si existen elementos que contienen estados. Por lo que, se debe ayudar a Vue con una llave que contenga un valor único para que sepa identificar a los elementos que pertenecen a la lista de contenidos.
# Methods
Se usa para enlazar eventos o enlazar datos. Los métodos se ejecutarán cada vez que se vuelva a renderizar el componente del que Vue tiene control.
Se usa para eventos o datos que necesitan ser re evaluados todo el tiempo.
# Computed properties
Se usa para enlazar datos que dependen de otros datos. A diferencia de methods, el valor solo se volverá a evaluar si el dato que se está evaluando cambia.
Funciona como methods, sin embargo, es recomendable usar computed properties para mostrar valores que se sabe que no necesitan ser reevaluados cada que algo pase en la página web.
# Watchers
Se usa para observar un dato y determinar una acción en base a el valor que tome el dato observado.
Permite ejecutar cualquier código siempre y cuando cambie el dato que se está observando.
# Vue por detrás
## Reactividad
Hay que tener una cosa en mente y es que JavaScript por defecto NO es reactivo, sino que eso es algo que Vue ofrece como tal.
``` JavaScript
let message = "Hello!";
let longMessage = message + " World!";
console.log(longMessage);   ==> Hello! World!

console.log('-------');

message = "Hello!!!!";
console.log(longMessage);   ==> Hello! World!
```
En el ejemplo anterior, como JavaScript no es reactivo, no vuelve a ejecutar el código lo que hace que la variable inicial no cambie y se mantenga el anterior.
En este aspecto, Vue tiene un mecanismo que si le permite estar al tanto cuando una variable cambia, para eso se usa algo denominado <mark style="background: #ADCCFFA6;">Proxy</mark> de JavaScript.
En código JS vanilla lo que se hace por detrás es lo siguiente:
```JavaScript
const data = {
  message: 'Hello!',
  longMessage: 'Hello! World!'
};

const handler = {
  set(target, key, value) {
    if (key === 'message'){
      target.longMessage = value + 'World!';
    }
    target.message = value;
  }
};
  
const proxy = new Proxy(data, handler);
proxy.message = 'Hello!!!'
console.log(proxy.longMessage);
```
Esto se puede resumir en lo siguiente:
>[!Note]
>Cada vez que se asigna un valor a una propiedad a través del proxy, el `set` puede hacer tareas adicionales, como actualizar otras propiedades dependientes (como `longMessage` en tu ejemplo).

Entonces lo que hace Vue por detrás es asignar un proxy a cada una de las variables (`data() { ... })` dentro de la aplicación, entonces, en el momento en que una de estas variables cambia la parte de la aplicación en donde la misma fue usada.
## Templates
Es una parte de la página web de la cual Vue tiene control.
>[!Note]
>Dentro de Vue se puede tener más de una aplicación que puede ser manipulada por Vue, valga la redundancia.
## Refs
Con refs podemos apuntar al objeto del DOM para un elemento en específico HTML.
```JavaScript
En HTML:
<input type="text" ref="userText" />

En JavaScript
console.log(this.message = this.$refs.userText); ==> <input type="text" />
```
## Vue instance lifecycle
![[Drawing 2025-05-08 14.42.07.excalidraw]]
# Componentes
Los componentes en Vue se crean a través de la aplicación creada con el método `component()` que sigue la siguiente estructura:
``` JavaScript
app.component(id, config_object)
```