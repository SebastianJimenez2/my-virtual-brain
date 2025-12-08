# Pages & Responses
Se usa 
``` PHP
function() {
	Inertia::render('PathRuta', [
	'propiedad' => $valor
	]);
}
```
# Redirects
Se puede usar
``` PHP
return to_route('route')
/* ------ */
return redirect()->route('route')
```
# Routing
Se usa
```PHP
 route('route', props)
 ```
# Title & meta
Se usa importando lo siguiente:
```PHP
import { Head } from '@inertiajs/vue3' 

<Head> 
	<title>Your page title</title> 
	<meta name="description" content="Your page description"> 
</Head>
```
# Links
Se usa de la siguiente forma, es como usar un anchor en esteroides:
```PHP
import { Link } from '@inertiajs/vue3' 

<Link href="/">Home</Link>

/* ------ */

// Se puede usar la propiedad 'as' para cambiar su apariencia, por ejemplo:
<Link href="/logout" method="post" as="button">Logout</Link> 

// Renders as... 
<button type="button">Logout</button>
```
>[!Note]
>El método por default que usa Link es GET. Para métodos POST o PUT se puede usar la propiedad `:data="{ foo: bar }`

Existen propiedades como:
- `preserve-scroll`para mantener la posición del scroll del navegador al hacer clic
- `preserve-state` para no perder la data de un input, por ejemplo
# Manual visits
Se hace usando:
```PHP
import { router } from '@inertiajs/vue3'

router.visit(url, {
  method: 'get',
  data: {},
  replace: false,
  preserveState: false,
  preserveScroll: false,
  only: [],
  except: [],
  headers: {},
  errorBag: null,
  forceFormData: false,
  queryStringArrayFormat: 'brackets',
  async: false,
  showProgress: true,
  fresh: false,
  reset: [],
  preserveUrl: false,
  prefetch: false,
  onCancelToken: cancelToken => {},
  onCancel: () => {},
  onBefore: visit => {},
  onStart: visit => {},
  onProgress: progress => {},
  onSuccess: page => {},
  onError: errors => {},
  onFinish: visit => {},
  onPrefetching: () => {},
  onPrefetched: () => {},
})
```
## Method
Se usa para el método de la solicitud HTTP:
- GET
- POST
- PUT
- PATCH
- DELETE
## Data
Se usa para mandar data a la página que se vaya a visitar
```PHP
import { router } from '@inertiajs/vue3'

router.visit('/users', {
  method: 'post',
  data: {
    name: 'John Doe',
    email: 'john.doe@example.com',
  },
})
```
## Headers
Se puede agregar headers personalizados a la solicitud:
```PHP
import { router } from '@inertiajs/vue3'

router.post('/users', data, {
  headers: {
    'Custom-Header': 'value',
  },
})
```
# Forms


