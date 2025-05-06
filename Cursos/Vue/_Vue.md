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
## v-bind
Se usa para asignar datos en nuestra aplicación de Vue a etiquetas HTML.
## v-html
Sirve para pasar datos con etiquetas html de una aplicación Vue a un archivo `.html`.
## v-on
Es para escuchar eventos, es decir, para definir qué pasa cuando se ejecuta una acción en específico.
## v-once
Hace que un evento dinámico solo cambie una vez, luego se mantendrá en un estado de "bloqueo".
## v-model
Es una forma de resumir la existencia de v-bind y v-on en un solo. A esto se le conoce como two-way binding, ya que se comunica en dos direcciones.
# Methods
Se usa para enlazar eventos o enlazar datos. Los métodos se ejecutarán cada vez que se vuelva a renderizar el componente del que Vue tiene control.
Se usa para eventos o datos que necesitan ser re evaluados todo el tiempo.
# Computed properties
Se usa para enlazar datos que dependen de otros datos. A diferencia de methods, el valor solo se volverá a evaluar si el dato que se está evaluando cambia.
Funciona como methods, sin embargo, es recomendable usar computed properties para mostrar valores que se sabe que no necesitan ser reevaluados cada que algo pase en la página web.
# Watchers
Se usa para observar un dato y determinar una acción en base a el valor que tome el dato observado.
Permite ejecutar cualquier código siempre y cuando cambie el dato que se está observando.