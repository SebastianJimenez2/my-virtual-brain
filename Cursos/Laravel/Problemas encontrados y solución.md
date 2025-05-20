# PHP artisan serve command don't listen any port
Al ejecutar `php artisan serve` se mostraba lo siguiente:
```cmd
Failed to listen on 127.0.0.1:8000 (reason: ?)
Failed to listen on 127.0.0.1:8001 (reason: ?)
Failed to listen on 127.0.0.1:8002 (reason: ?)
Failed to listen on 127.0.0.1:8003 (reason: ?)
Failed to listen on 127.0.0.1:8004 (reason: ?)
Failed to listen on 127.0.0.1:8005 (reason: ?)
Failed to listen on 127.0.0.1:8006 (reason: ?)
Failed to listen on 127.0.0.1:8007 (reason: ?)
Failed to listen on 127.0.0.1:8008 (reason: ?)
Failed to listen on 127.0.0.1:8009 (reason: ?)
Failed to listen on 127.0.0.1:8010 (reason: ?)
```
Para solucionar esto:
1. Descargar Herd es una de las posibles soluciones, sin embargo, esto solo hará más robusto al archivo `php.ini` que es en donde residía el problema, dentro de ese archivo existe una variable: `variables_order = "EGPCS"` la cual debe ser modificada a `variables_order = "GPCS"` guardar, reiniciar la terminal y ejecutar de nuevo el comando.
# Unknown database
Al momento de querer ejecutar el comando `php artisan serve` sale el siguiente error:
```
SQLSTATE[HY000] [1049] Unknown database 'XXXX' (Connection: mysql, SQL: select * from `sessions` where `id` = QLzEA4lCsgAXbjcoWrd1tPPJCGqSYukpZsYUR7Cm limit 1)
```
Para solucionar:
- Asegurarse de que exista la BD
- `php artisan migrate`
# Route is not routing (web.php)
Al agregar una nueva ruta, crear la vista y querer usar sigue apareciendo como que no existe o no he creado el archivo.
Solución:
- Cancelar la ejecución del servidor
- `php artisan optimize`
- `php artisan serve`
>[!Note]
>No es la solución más óptima ya que se tiene que hacer a cada rato, pero no he encontrado otra solución. Problema del Sebas del futuro.

