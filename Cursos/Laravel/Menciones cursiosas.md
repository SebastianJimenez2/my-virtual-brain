# Para ver los queries hechos a una DB
```PHP
Route::get('/', function() {
	\Illuminate\Support\Facade\DB::listen(function($query) {
		logger($query->sql, $query->binding)
	})
})
```
>[!Note]
>También se puede usar [clockwork](https://github.com/itsgoingd/clockwork) instalando la dependencia en el programa y la extensión en el navegador.
# Ver todas las rutas
```PHP
php artisan route:list
```