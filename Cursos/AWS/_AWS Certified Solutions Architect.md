# Docker
| Contenedor                                | Maquina Virtual                      |
| ----------------------------------------- | ------------------------------------ |
| Un contenedor tiene un 'container engine' | La máquina virtual usa un hipervisor |
![[Containers vs VM.png]]
**Contenedor.** Conjunto de elementos donde podemos tener una aplicación con sus dependencias. 

> Un [[Docker file]] construye una imagen, y la imagen ejecuta un contenedor.
### Build an image
```
docker build -t <image-name>:<tag> .
```

---
# CLOUD
- #### [[AWS Snowmobile]]
- #### [[Cloud Computing]]
- #### [[Service Categories]]
- #### [[Account Administration]]
# Infraestructura como Código [[IaaS]]
Todo está especificado como código. 
# Terraform
Es una herramienta IaaS que nos permite provisionar y manejar de manera segura a infraestructura en cualquier nube.
- ### [[Comandos]]
# VPC
**Public Subnet.** 
**Private Subnet.** 
**Route table.** Cada subnet debe estar asociada a una tabla de rutas que especifica las turas permitidas para el tráfico de la subred.
# Crear una instancia EC2
>Amazon EC2 provides on-demand, scalable computing capacity in the AWS Cloud
### Amazon EC2
- **Instances**. Virtual servers
- **Amazon Machine Images**. Templates preconfigurados para las instancias que empaqueta los componentes que se necesitan para el servidor.
- **Instance Types**. Configuraciones varias del CPU, memoria, almacenamiento, networking, capacidad y gráficos de hardware para las instancias.
- **Key pairs**. Información segura de login para las instancias. AWS almacena la llave pública y nosotros la llave privada en un lugar seguro.
### Grupo de seguridad
> Un firewall nos permite controlar el tráfico de red entrante y saliente.

Se basa en el concepto de firewall, pero no se limita solo a la red sino al recurso de TI.
### Tipos de virtualización
- **HVM.** Busca hacer una simulación de un host como si fuese uno físico.
- Muchas virtualizaciones que dependen del host padre, si muere el padre mueren los demás.
---
# AWS RE: Invent
Amazon ECS. 