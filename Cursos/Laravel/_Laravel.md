# ARCHIVOS IMPORTANTES
## INDEX.PHP
`public/index.php` 
> Todas las solicitudes son redirigidas a este archivo por el servidor web

## WEB.PHP
Para redirigir entre páginas, se usa el archivo `routes/web.php`, definiendo las rutas de la siguiente forma:
```js
Route::get('posts', function () {
    return "Aqui van los posts";
});
```
> Esta función mostrará en pantalla el mensaje especificado. Tomar en cuenta que se puede cambiar get por: `post`, `put`, `patch` y `delete` según sea el caso necesario.

También existe una forma de mandar parámetros:
```js
//Rutas con parametros
Route::get('posts/{post}', function ($post) {
    return "Aqui va el post con id: $post";
});

//Rutas con parametros opcionales
Route::get('posts/{post}/{categoria?}', function ($post, $categoria = null) {
    if ($categoria) {
        return "Aqui va el post con id: $post y categoria: $categoria";
    } else {
        return "Aqui va el post con id: $post";
    }
});
```
> Es importante el orden en que se definan las rutas, ya que si existen rutas con URIs similares, se accederá a la que fue definida en primer lugar.

# CONTROLADORES
Un controlador es el encargado de procesar las solicitudes de los clientes de una manera más organizada. Una forma fácil de crear controladores es usando artisan de la siguiente forma:
```php
php artisan make:controller <nombreController> 
```
Este comando creará un archivo con el nombre especificado en la ruta `app/Http/Controller` con la siguiente estructura:
```php
<?php
namespace App\Http\Controllers;
use Inertia\Inertia;
use Illuminate\Http\Request;

class <nombreController> extends Controller
{
    ...
}
```
Los controladores permiten organizar la estructura del archivo `web.php` ya que simplifica la información y se aplica el principio de responsabilidad única.
```php
<?php

use App\Http\Controllers\HomeController;
use App\Http\Controllers\PostController;

Route::get('/', HomeController::class); // [1]

# Rutas de posts
Route::get('posts', [PostController::class, 'index']);
Route::get('posts/{post}', [PostController::class, 'show']);
Route::get('posts/create', [PostController::class, 'create']);
Route::get('posts/{post}/{categoria?}', [PostController::class, 'showCategory']);
```
> Si un controlador tiene un solo método el mismo puede ser reemplazado por `__invoke()`, evitando especificar el método en el llamado al controlador (Véase [1]).

# VISTAS
Las vistas es lo que el usuario observa luego de realizar una petición, en el proyecto se encuentran en `resources/views`
> En esta carpeta se encuentran vistas con extensión `.blade.php`, si se desea desarrollar usando Vue.js los templates se encuentran en `resources/js/pages`

Para llamar del controlador a la vista se usa el siguiente método dentro de la función especificada en `web.php`:
```php
public function index()
    {
        return view('posts.index');
    }
```

> En el caso de usar Vue.js se puede usar Inertia: `return Inertia::render('...');`

En el caso de las funciones con parámetros:
```php
public function show($post)
    {
        return view('posts.show', compact('post'));
    }
```
Compact es una función de php que lo que hace es mandar la variable definida desde el back-end hacia el front-end de forma compacta a lo que era anteriormente: 
```php
public function show($post)
    {
        return view('posts.show', [
	        'post' => $post
        ]);
    }
```
Entonces, por parte del front, la variable se recibe de la siguiente forma:
```html
<body>
    <h1> Aquí va el post de {{ $post }} </h1>

	<!-- 
	Blade permite usar condicionales y estructuras en php usando @, por 
	ejemplo:
	@if (true)
		<p> Hola </p>
	@endif
	-->
</body>
```

## COMPONENTES
Ayuda a evitar la repetición de código, se encuentran en `resources/views/components`, dentro del directorio se crea un componente y es llamado en la vista a manera de una etiqueta html.
### Componente anónimo
```html
@props(['type' => 'info'])

@php
    switch ($type) {
        case 'info':
            $class = 'text-blue-800 bg-blue-50 dark:bg-gray-800 dark:text-blue-400';
            break;

        case 'danger':
            $class = 'text-red-800 bg-red-50 dark:bg-gray-800 dark:text-red-400';
            break;
            
        case 'success':
            $class = 'text-green-800 bg-green-50 dark:bg-gray-800 dark:text-green-400';
            break;

        case 'warning':
            $class = 'text-yellow-800 bg-yellow-50 dark:bg-gray-800 dark:text-yellow-400';
            break;

        default:
            $class = 'text-blue-800 bg-blue-50 dark:bg-gray-800 dark:text-blue-400';
            break;
    }
@endphp
  
<div class="p-4 mb-4 text-sm rounded-lg {{ $class }}" role="alert">
    <span class="font-medium"> {{ $title ?? 'Info Alert!' }} </span> {{ $slot }}
</div>
```
### Vista
```html
<body>
    <div class="max-w-2xl mx-auto p-4">
        <x-alert type="danger">
            <x-slot name="title" >
                Información
            </x-slot>
            Hola
        </x-alert>
    </div>
</body>
```
### Componente de clase
El objetivo del componente de clase es usar la menor cantidad de lógica en el componente, para esto se usa el siguiente comando:
```php
php artisan make:component <nombreComponente> 
```
Este comando crea dos archivos:
1. `app/View/Components/<nombreComponente>.php`, en donde se pondrá la lógica
2. `resources/views/components/<nombreComponente>.blade.php`, en donde se especificará el html del componente
# BASES DE DATOS
### Conexión
Laravel por defecto se conecta a sqlite, sin embargo, si se quiere cambiar este valor, debemos observar o cambiar las opciones que se tiene dentro del archivo `config/database.php` en `connections`
> La conexión es establecida en el archivo `.env` en la variable `DB_CONNECTION`, abajo de esta se deben establecer los valores para conectarse a la base elegida.

```.env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=blog
DB_USERNAME=root
DB_PASSWORD=
```

Para probar usaremos el comando `php artisan migrate` y se deben crear las tablas específicas de Laravel.
### Migraciones
Las migraciones se encuentran en el directorio `database/migraciones` y se ven de la siguiente forma
```php
<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    /**
     * Run the migrations.
     */
    public function up(): void
    {
        Schema::create('users', function (Blueprint $table) {
            $table->id();
            $table->string('name');
            //Evite la existencia de dos registros con el mismo email
            $table->string('email')->unique(); 
            //Puede tomar el valor de null
            $table->timestamp('email_verified_at')->nullable(); 
            $table->string('password');
            // Token de seguridad
            $table->rememberToken();
            // Crea dos campos, cuándo se creo el registro y cuando se 
	        // actualizó
            $table->timestamps();
        });

        Schema::create('password_reset_tokens', function (Blueprint $table) {
            $table->string('email')->primary();
            $table->string('token');
            $table->timestamp('created_at')->nullable();
        });

        Schema::create('sessions', function (Blueprint $table) {
            $table->string('id')->primary();
            $table->foreignId('user_id')->nullable()->index();
            $table->string('ip_address', 45)->nullable();
            $table->text('user_agent')->nullable();
            $table->longText('payload');
            $table->integer('last_activity')->index();
        });
    }

    /**
     * Reverse the migrations.
     */
    public function down(): void
    {
        Schema::dropIfExists('users');
        Schema::dropIfExists('password_reset_tokens');
        Schema::dropIfExists('sessions');
    }
};
```
> Existen dos funciones dentro de las migraciones `up()` y `down()` que sirven para crear las migraciones, las esquemas y la otra para eliminar los esquemas en caso que se haga rollback. Una misma migración puede crear más de una tabla.
### CREAR Y DESHACE MIGRACIÓN
Para hacer una migración se usa el siguiente comando:
```php
php artisan migrate
```
> Este comando creará las tablas dentro del método `up()`

Para hacer rollback se usa el siguiente comando:
```php
php artisan migrate:rollback
```
> Este comando creará las tablas dentro del método `down()`

Al hacer migraciones las hace en bloques, dentro de la BDD se encontrará una tabla llamada "migraciones", en esta tabla se encuentra la migración que se ha hecho y el batch, es decir, el bloque en el que se hizo, si se quiere especificar que tanto se desea hacer rollback acorde al batch, se debe acompañar al comando de `--step=n`. Si no se especifica, siempre se hará el rollback del último lote.
### CREAR ESQUEMAS
Para crear esquemas se usa el siguiente comando
```php
php artisan make:migration create_<nombre>_table
```
Creando un archivo en `database/migraciones` con la siguiente estructura:
```php
<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    /**
     * Run the migrations.
     */
    public function up(): void
    {
        Schema::create('posts', function (Blueprint $table) {
            $table->id();
			// Creado manualmente
            $table->string('title');
            $table->text('content');
            $table->string('categoria');
			// Fin
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     */
    public function down(): void
    {
        Schema::dropIfExists('posts');
    }
};
```
### REFRESCAR MIGRACIONES
Para eliminar todas las migraciones y volverlas a crear se usa el siguiente comando:
```php
php artisan migrate:refresh 
```
### ELIMINAR MIGRACIONES
Eliminar todas las tablas y migraciones y empezar desde 0 se usa:
```php
php artisan migrate:fresh 
```

> Al usar tanto refresh, fresh y rollback se eliminan los registros existentes dentro de las tablas ya que son métodos destructivos.

### AUMENTAR COLUMNA EN MIGRACIÓN SIN ELIMINAR REGISTROS
Como los comandos anteriores son destructivos, cada que se ejecuten se eliminan los registros de la BDD, para evitar esto se usa el siguiente comando:
```php
artisan make:migration add_<columna>_to_<nombre_tabla>_table
```
Este comando creará una migración con la diferencia de que ya no creará un esquema, sino que hará referencia al ya existente:
```php
return new class extends Migration
{
    /**
     * Run the migrations.
     */
    public function up(): void
    {
        Schema::table('users', function (Blueprint $table) {
	        // Agregado manualmente, SIEMPRE debe ser nullable
	        // after() crea la columna después de la columna especificada
            $table->string('avatar')->nullable()->after('name');
        });
    }

    /**
     * Reverse the migrations.
     */
    public function down(): void
    {
        Schema::table('users', function (Blueprint $table) {
	        // Agregado manualmente
            $table->dropColumn('avatar');
        });
    }
};
```
# MODELOS
Para crear modelos se usa el siguiente comando
```php
php artisan make:model <Nombre>
```
Esto creará el modelo con el nombre especificado en la ruta `app/Models`
```php
<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Model;

class Post extends Model
{
    protected $table = 'posts';
}
```
# SEEDERS
Son datos quemados dentro de la base de datos para probar funcionalidades con los registros reales. Estos datos se realiza dentro de la carpeta `database/seeder/*.php`.
Y se alimenta a la base de datos usando el siguiente comando:
```php
php artisan db:seed
```
Pueden existir tantos seeder se desee creando archivos `.php` dentro de la carpeta. PAra esto se puede usar el siguiente comando
```php
php artisan make:seeder <nombre>
```
Para migrar tablas y ejecutar los seeders se usa el siguiente comando:
```php
php artisan migrate:fresh --seed
```
# FACTORIES
Insertan registros a las tablas. Son fábricas que especifica qué se va a crear en cada campo y la inserción de registros. Para crearlo se usa el siguiente comando:
```php
php artisan make:factory <nombre>
```

```php
php artisan migrate:fresh --seed
```

