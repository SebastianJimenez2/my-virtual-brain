- En los sistemas lo que mas importa es la información.
- La criptografía es el conjunto de varias técnicas
- Sensitive Data Exposure
- El A02 se enfoca en la criptografía, en el mal uso de las mismas, en las fallas o ausencias
La criptografía es el estudio de técnicas de comunicación segura para que tanto el que envía y como el que recibe el mensaje tenga el derecho a entenderlo.
La encriptación está dentro de la criptografía, siendo una técnica de las muchas existentes.
![[Pasted_image_20220629203516.png]]
1. El primer fallo en este aspecto es quemar las contraseñas, IP o cosas que no deberían conocer todos
2. Otro fallo es la elección de un algoritmo que es malo, o fácil de vulnerar. --> Broken or Risky Crypto Algorithm
3. Por otro lado se tiene la entropía, ques básicamente es cuando seleccionas un servidor que no tiene tantas capacidades cuando la aplicación pide más cosas.
### Hashing
Hashing es un método de la criptografía, permite convertir un texto a través de una función hash, para obtener un resultante diferente.
La función 'hash' tiene una lógica y depende de lo que utilice para obtener el resultante que básicamente una cadena de String (código Hexadecimales) de una longitud en específico.
MD5 (Message-Digest Algorithm 5) --> es justamente una hash function, orientado a la seguridad informática.
Vamos a tener un input que puede ser una cadena de texto (data input) se le pasa por el algoritmo MD5 (que va a usar una función hash que va a transformar algo en otra cosa) obteniendo un resultante (checksum) de 32 códigos hexadecimales. Esto se usa cuando se habla en la parte de contraseñas.
Los hashes son únicos para cada input.
Ronald Rives es el creador del rsa, aportante de la criptografía y era del MIT.
El error es que si alguien pone de contraseña 'admin123' y guarda en la base de datos esa misma contraseña pero como salida de MD5, sigue sin ser 100% seguro.
Hashcat utiliza tu máquina, tu CPU o GPU, para que haga un cracking de contraseñas.
### Comando
```Plain
hashcat -m 0 hashes rockyou.txt
-m 0        --> Hashcat mode: 0 is MD5
hashes      --> archivo que tiene el hash (contraseña que está hasheada)
rockyou.txt --> wordlist
```
Un 'wordlist' es una diccionario de contraseñas, es tener un archivo donde se tenga las contraseñas mas populares e incluso filtradas de los usuarios, generalmente sirve para hacer ataques de fuerza bruta. Es decir, comparar algo e igualar hasta que se obtenga algo del diccionario.
En nuestro caso va a buscar, comparando nuestra password hasheada que es lo que un atacante pudo obtener de una filtración de información de la base de datos.
### Rockyou.txt
Este archivo tiene bastantes contraseñas que son muy usadas a nivel mundial y contraseñas que no tienen buenas políticas de seguridad.
**En parrot**
- Menú
- Wordlist
- rockyou.txt
```Plain
1. sudo gunzip rock.you.txt.gz --> Permite descomprimir el gz que se tenía antes.
2. ls --> debe aparecer el archivo 'rockyou.txt' sin el .gz
3. cat rockyou.txt --> aparecen bastantes contraseñas
4. cp rockyou.txt ~/Desktop --> mover algo de un lugar a otro
	=> cd ~ == cd <user>
5. echo -n "1234" | md5sum | tr -d " -" >> hashes
6. hashcat -m 0 hashes rockyou.txt
```
### Medidas de prevención
1. Nunca guardar este tipo de contraseñas en texto plano
2. No seleccionar un algoritmo de hashing débil
3. Utilizar PBKDF2 (password base key derivated function 2) que además del password busca hacer un hash pero aplicando un 'salt' (obtener un número o strings aleatorio)
### Scrypt, Bcrypt and ARGON2
Estos dejan de lado el SHA, MD5 y buscan tener más medidas de seguridad, además de ser más complejos. Sería bueno aplicar ARGON2.