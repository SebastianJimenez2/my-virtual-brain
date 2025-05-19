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
# Estructura de un proyecto Vue
## main.js
Punto de entrada principal, es en dónde se crea la aplicación.
## App.vue
Es en donde se especifica un módulo de una app de Vue, contiene tres cosas principales:
- `<template>`
- `<script>`
- `<style>`
>[!Note]
>Los estilos que se pongan en un componente afectan a toda la app, para que un estilo afecte a un solo componente se debe usar `<style scoped>`
# Componentes
Los componentes en Vue se crean a través de la aplicación creada con el método `component()` que sigue la siguiente estructura:
``` JavaScript
app.component(id, config_object)
```
Se tiene la opción de importar los componentes locales y globales, se sugiero hacerlo global cuando más de un template usa el componente, sino, se puede hacer la importación local.
## Componentes con slot
Al crear un componente usando slot, por ejemplo:
```JavaScript
<template>
  <div>
    <header v-if="$slots.header">  // esta condicional verifica si vamos a recibir contenido para renderizarlo, caso contrario no lo renderiza.
      <slot name="header">
        <!-- <h2>Default Header</h2> -->
      </slot>
    </header>
    <slot> </slot>
  </div>
</template>
```
Entonces, si usamos este componente en otro componente:
``` JavaScript
<template>
  <section>
    <base-card>
      <template v-slot:(or #)header>
        <h3>{{ fullName }}</h3>
        <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
      </template>
      <template v-slot:default>
        <p>{{ infoText }}</p>
      </template>
    </base-card>
  </section>

</template>
```
Se ha de notar los siguiente:
- `v-slot:default` apunta al slot que no está siendo asignado ningún nombre, y los elementos del componente se pondrán ahí.
- Si no se tiene `v-slot:name`, entonces, tomará el valor de default siempre y cuando este exista en el slot
## Componentes dinámicos
Vue nos ofrece una etiqueta para hacer la vida más sencilla de los devs `<component/>`, funcionado de la siguiente forma:
```JavaScript
<div>
    <the-header></the-header>
    <button @click="setSelectedComponent('active-goals')">Active Goals</button>
    <button @click="setSelectedComponent('manage-goals')">Manage Goals</button>
    <!-- active-goals v-if="selectedComponent == 'active-goals'"></active-goals -->
    <!-- manage-goals v-if="selectedComponent == 'manage-goals'"></manage-goals> -->
    <component :is="selectedComponent">
    </component>
  </div>
```
Nótese cómo `<componente/>` simplificó dos condicionales en una solo línea,
# Component communication
## Properties (props) (parent => child)
Son los atributos que un componente puede aceptar.
```
props: [
	'name',
    'phoneNumber',
    'emailAddress'
]
```
Básicamente es una forma de comunicar las propiedades desde padre hacía el hijo. Al realizar este proceso de comunicación, las propiedades del padre no pueden ser modificadas en el hijo, es decir, no son ==mutables==.
## Custom events (child => parent)
`$emit(<name-custom-event>, data ...)` permite emitir un evento que se puede escuchar en el  componente del padre. El evento que se emite desde el hijo, el padre lo puede escuchar con `v-on o @<name-custom-event>="código JS"`. Estos eventos pueden tener datos que luego podrán ser usados en el método que haga su llamado.
## Provide and inject pattern-
### Problema 
A veces hay datos que necesitan ser enviados a través de muchos componentes (pass-through) lo que genera mucha dependencia. Alto acoplamiento.
![[Pasted image 20250509163037.png]]
### Solución
Con provide-inject lo que se hace es proporcionar datos desde un componente padre, para ser inyectado a un componente hijo.
>[!Warning]
>Para inyectar datos SI O SI deben venir de un componente padre, no se puede proveer de un hijo e inyectar al padre.

![[Pasted image 20250509160224.png]]
# Forms
Para extraer datos de un input de tipo texto asociado a un forms se puede usar `v-model` asociado a un dato creado previamente dentro del mismo componente, que es la variable en donde se guardará la información ingresada por el usuario. 
>[!Note]
>La diferencia de v-model y refs es que v-model devuelve el tipo que tenga en input al valor, en cambio, refs todo lo devuelve como texto.
>

En caso de que se tenga check-boxes o radio-buttons selectors, es importante asignar un `value=""` para que v-model sepa diferenciar entre los diferentes tipos de opciones.
# Backend
Para enviar información desde el front hacia el back (una base de datos, por ejemplo) se usa el ya conocido `fetch()` de la siguiente forma:
``` JavaScript
fetch(
        'https://vue-http-demo-68a66-default-rtdb.firebaseio.com/surveys.json',
        {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify({
            name: this.enteredName,
            rating: this.chosenRating,
          }),
        }
      );
```
>[!Note]
>En `methods` se puede usar cualquiera de los ya conocidos: PUT, PATCH, DELETE, POST, GET, sin embargo, la estructura del `fetch` cambia para cada una de estas.
## Método GET
Para recibir datos del back al front, se usa el método GET, el cual en la función `fetch()` está por defecto, por lo que no es necesario especificar. Entonces, para obtener los datos, se usa la función `fetch().then()` para obtener la respuesta y luego otro `.then()` para procesar la respuesta:
``` JavaScript
fetch(
        'https://vue-http-demo-68a66-default-rtdb.firebaseio.com/surveys.json'
      )
        .then((response) => {
          if (response.ok) {
            return response.json(); // obtiene la información si es recibida en JSON
          }
        })
        .then((data) => {
          const results = [];
          for (const id in data) {
            results.push({
              id: id,
              name: data[id].name,
              rating: data[id].rating,
            });
          }
          this.results = results;
        });
```
>[!Note]
>La función `then()` siempre requiere como parámetro a una función flecha en dónde se procesa toda la info necesaria obtenida.
# Routing
El routing sirve para especificar una URL a una acción específica o vista específica dentro de la aplicación web, para esto Vue ofrece `vue-router` el cuál se instala con el comando `npm install --save vue-router` y se usa de la siguiente forma:
``` JavaScript
import { createRouter, createWebHistory } from 'vue-router';

const router = createRouter({
    history: createWebHistory(), //sirve para que se guarden las rutas en el navegador
    routes: [
      { path: '/', redirect: '/teams' }
    ] // se especifica el array de las rutas
});
```
>[!Note]
>En la definición de la ruta, se puede agregar una llave denominada "name" para asociar la ruta con un nombre o id específico, adicional a esto, si dentro de esa ruta se quiere renderizar más de un componente con `<router-view>`, se puede usar la llave `components` y como slots, dar un nombre al `router-view` y especificar el componente que se quiere renderizar en ese nombre asociado.

Una vez definido, para usarlo, se tiene la etiqueta `<router-link to="/ruta-especificada"></router-link>` de la siguiente forma:
``` JavaScript
<template>
  <header>
    <nav>
      <ul>
        <li>
          <router-link to="/teams">Teams</router-link>
        </li>
        <li>
          <router-link to="/users">Users</router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>
```
>[!Note]
>En realidad, la etiqueta usada `<router-link>` para el enrutamiento es un anchor `<a>` por detrás, así que funciona como tal.

También al instalar el paquete, disponemos de `$router` accesible en cualquier componente, que junto con métodos puede ayudar a programar un botón para que funcione como un navegador entre rutas:
``` JavaScript
<template>
  <button @click="confirm()">Confirm</button>
</template>

<script>
export default {
  methods: {
    confirm() {
      this.$router.push('/teams'); //también existe .forward() o .back() que simulan los botones de navegación del navegador y muchos métodos más disponibles en la documentación
    },
  },
};
</script>
```
Cuando estás en una página por ejemplos `your.domain/teams/t2` y quieres navegar dentro de esa página a `your.domain/teams/t1`, es decir, cambiando el valor del parámetro de la URL, se debe tener en cuenta que `router` no destruye y vuelve a construir los componentes que han sido cargados cuando navegas por ellos, sino que los atrapa, por lo que pese a que la URL cambia, el contenido no cambiará, para esto se hace lo siguiente:
```JavaScript
// Se crea un método del encargado de lidear con las rutes, es decir, route.
   methods: {
    loadTeamMembers(route) {
      const teamId = route.params.teamId;
      const selectedTeam = this.teams.find((team) => team.id === teamId);
      const members = selectedTeam.members;
      const selectedMembers = [];
      for (const member of members) {
        const selectedUser = this.users.find((user) => user.id === member);
        selectedMembers.push(selectedUser);
      }
      this.members = selectedMembers;
      this.teamName = selectedTeam.name;
    },
  },

// Llamamos el método cada que el componente se crea
  created() {
    this.loadTeamMembers(this.$route);
  },

// Llamamos el método cada que la ruta cambia, aquí solventamos el problema, cada que cambie la ruta, se volverá a crear al componente
  watch: {
    $route(newRoute) {
      this.loadTeamMembers(newRoute)
    },
  },
```
>[!Note]
>Una alternativa adicional a la solución anterior es recibir como parámetro un prop en lugar del route para hacerlo más reusable, ya que se podrá acceder a esa URL siempre y cuando el otro componente tenga como prop al parámetro enviado, para eso hay que tener en consideración que se debe especificar en el path que se aceptan props:
>`{ path: '/teams/:teamId', component: TeamMembers, props: true }`

# Transition tag
Un problema que se tiene con CSS es que luego de realizar una animación, la misma se destruye por lo que no es posible regresar a su estado natural con animación sino que se hace de forma abrupta, para esto Vue ofrece `<Transition>`, que funciona de la siguiente forma:
![[Pasted image 20250515174248.png]]
En donde:
- **v-enter-from:** Estado inicial para entrar. Añadido antes de insertar el elemento, eliminado un fotograma después de insertar el elemento.
- **v-enter-active:** Estado activo para entrar. Se aplica durante toda la fase de entrada. Se añade antes de insertar el elemento y se elimina al finalizar la transición/animación. Esta clase permite definir la duración, el retardo y la curva de relajación de la transición de entrada.
- **v-enter-to:** Estado final para entrar. Se añade un fotograma después de insertar el elemento (al mismo tiempo que se elimina v-enter-from) y se elimina cuando finaliza la transición/animación.
- **v-leave-from:** Estado inicial de leave. Se añade inmediatamente cuando se activa una transición de salida, se elimina después de un fotograma.
- **v-leave-active:** Estado activo de la salida. Se aplica durante toda la fase de abandono. Se añade inmediatamente cuando se activa una transición de salida y se elimina cuando finaliza la transición/animación. Esta clase puede utilizarse para definir la duración, el retardo y la curva de relajación de la transición de salida.
- **v-leave-to:** Estado final de la salida. Se añade un fotograma después de que se active una transición de salida (al mismo tiempo que se elimina v-leave-from) y se elimina cuando finaliza la transición/animación.
>[!Note]
>Se puede asignar un nombre al tag de transition y se reemplaza la `v` por el nombre puesto al tag. Además, hay que tener en cuenta que el mismo solo puede envolver a un elemento a ser animado, a excepción de si se usa `v-if / v-else`
## JavaScript hooks
```JavaScript
<Transition
  @before-enter="onBeforeEnter"
  @enter="onEnter"
  @after-enter="onAfterEnter"
  @enter-cancelled="onEnterCancelled"
  @before-leave="onBeforeLeave"
  @leave="onLeave"
  @after-leave="onAfterLeave"
  @leave-cancelled="onLeaveCancelled"
>
  <!-- ... -->
</Transition>


// called before the element is inserted into the DOM.
// use this to set the "enter-from" state of the element
function onBeforeEnter(el) {}

// called one frame after the element is inserted.
// use this to start the entering animation.
function onEnter(el, done) {
  // call the done callback to indicate transition end
  // optional if used in combination with CSS
  done()
}

// called when the enter transition has finished.
function onAfterEnter(el) {}

// called when the enter transition is cancelled before completion.
function onEnterCancelled(el) {}

// called before the leave hook.
// Most of the time, you should just use the leave hook
function onBeforeLeave(el) {}

// called when the leave transition starts.
// use this to start the leaving animation.
function onLeave(el, done) {
  // call the done callback to indicate transition end
  // optional if used in combination with CSS
  done()
}

// called when the leave transition has finished and the
// element has been removed from the DOM.
function onAfterLeave(el) {}

// only available with v-show transitions
function onLeaveCancelled(el) {}
```
# Vuex replacing provide-inject pattern
![[Drawing 2025-05-16 16.29.56.excalidraw]]
Para empezar a usar Vuex se debe usar lo siguiente dentro de `main.js`
```JavaScript
import { createStore } from 'vuex'

const store = createStore ({
	state() {
		return {
			// definir variables que todos los componentes pueden usar con this.$store.state.<variable>
		}
	},
	mutations() {
		// definir métodos que se van a usar en todos los compoenente con this.$store.commit(<método>)
		método(state) {
			state.variable //state te permite acceder a las variables definidas dentro de los métodos
		}
		método(state, payload){
			// payload es una variable de cualquier tipo que se va a recibir al llamar al método (puede tomar cualquier nombre, no necesariamente payload)
			// para usar este método se usa this.$store.commit(<método>, variable)
		}
	},
	actions () {
		// dado a que las mutaciones no deben tener código asíncrono, para usar métodos asincrónicos se usa actions
		método(context, payload) {
			// lógica ... {
				context.commit('mutación');
				context.dispatch('dispatchMethod');
				context.getters('getterMethod');
			// }
		}		
		// para usar estos métodos se usa this.$store.dispatch('método')
	},
	getters() {
		// se usa para obtener variables fijas que cambian acorde a un proceso
		método(state) {
			return state.variable * 2;
			// para usarlo se usa this.$store.getters.<metodoGetter>
		}
		método(_, getters) {
			// se usa _ cuando se quiere acceder a una segunda variable sin definir o usar la primera
			// este método sirve para acceder a otros getters definidos y en base a estos definir lógica y evitar el copy&paste smell
		}
	}
})
```
## Helpers
Sirven para reducir código y ser más claros al momento de llamar `actions` o `getters` dentro de componentes
```JavaScript
import { mapGetters } from 'vuex'
import { mapActions } from 'vuex'

computed () {
	...mapGetters(['getterMethod']) // dentro de computed propierties del componente
}

methods() { 
	...mapActions(['actionMethod1', 'actionMethos2', ...]) // dentro de methods propierties del componente
	// otra forma de usarlo
	...mapActions({
		nombre1: 'actionMethod1',
		nombre2: 'actionMethod2',
	})
}
```
## Organizing storage with modules
Se puede mejorar el storage dando responsabilidades únicas a objetos JavaScript que contengan la lógica de cada storage dividida.
```JavaScript
const nameModule = {
	state() {
		return {
			<variables-del-módulo>
		}
	},
	mutations: {
		mutaciones-del-módulo()
	},
	actions: {
		acciones-del-módulo()
	},
	getters: {
		getters-del-módulo()
	}
}

...........

const store = createStore ({
	modules: {
		nombreDelModuloCreado: nameModule
	}
```

