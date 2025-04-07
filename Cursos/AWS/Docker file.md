Proporciona instrucciones para construir una imagen de un contenedor mediante comandos

| INSTRUCCION | DESCRIPCION | EJEMPLO |
|---|----|---|
| **FROM**    | Se utiliza para especificar de donde se va a obtener la imagen  | node:20.11.1-alpine3.19 |
| **WORKDIR** | Se utiliza para establecer el directorio de trabajo dentro del contenedor donde se ejecutaran los comandos siguientes. Va a cambiarte entre rutas y sobre ese lugar va a ejecutar los comandos | /usr/src/app            |
| **COPY**    | Copiar archivos o direcciones desde la maquina host al sistema de archivos del contendor                                                                                                       | package*.json ./        |
| **RUN**     | Permite ejecutar comando durante el proceso de construccion                                                                                                                                    | npm install             |
| **EXPOSE**  | Se utiliza para exponer puertos dentro del contenedor y permitir que las aplicaciones dentro del contenedor escuchen conexiones en esos puertos                                                | 3006                    |
| **CMD**     | Se utiliza para especificar el comando predeterminado que se ejecutara al iniciar el contenedor                                                                                                | ["node", "index.js]     |
