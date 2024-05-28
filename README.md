# **DESAFIO 3**
---
## Objetivos del desafío: El objetivo de este desafío será crear algunos servicios básicos en nuestra cuenta de AWS e interactuar con ellos. Primero tendremos que verificar los prerrequisitos, en caso de ya cumplirlos, aclararlo en el instructivo. Luego crearemos una instancia EC2, un bucket S3 y un volumen de EBS:

1. **Creación del usuario IAM:**
   - Crearemos el usuario siguiendo los siguientes pasos:
   
   - Paso 1

    https://i.postimg.cc/W3XcHvRv/1.png
   
   - Buscamos el recurso en la barra de búsqueda de la plataforma con las palabras AIM y seleccionamos el recurso. 

   - Paso 2:

   https://i.postimg.cc/MZ380qb0/2.png
   

   Buscamos Usuarios y le damos click

   - Paso 3.
  

2. **Exponer Jenkins usando ngrok:**
   - Abre una terminal y ejecuta el siguiente comando:
     ```
     ngrok http http://localhost:8080
     ```
   - Esto proporcionará un enlace público para acceder a Jenkins.
     -(https://postimg.cc/wyxCYR2s)

3. **Acceder a Jenkins a través de ngrok:**
   - Abre tu navegador web y ve al enlace proporcionado por ngrok.
     - Dirección IP [https://f9b1-2802-8010-821d-e200-b0b3-141-3b8b-4a06.ngrok-free.app](https://f9b1-2802-8010-821d-e200-b0b3-141-3b8b-4a06.ngrok-free.app)
     - Acceder a Jenkins (https://postimg.cc/K3zv2z7z) 

4. **Configuración del webhook en GitHub:**
   - En la configuración de tu repositorio en GitHub, agrega una nueva URL de webhook apuntando al enlace de ngrok para los eventos "push" y "pull request".
   - Configurar webhook en GitHub (https://postimg.cc/WdNs30F4) 
   - Seleccionar eventos en GitHub (https://postimg.cc/V5d8sN3P) 

5. **Configuración de Jenkins para recibir notificaciones de GitHub:**
   - En Jenkins, configura un nuevo pipeline o proyecto y agrega las credenciales de GitHub.
     - Asegúrate de agregar la URL del repositorio de GitHub.
     - (https://postimg.cc/CBbbb02h) 
   - Activar la opción "GitHub hook trigger for GITScm polling" en Jenkins para que se accione como un gatillo que activa la construcción automática del proyecto cuando se produce un cambio en el repositorio de GitHub
     -(https://postimg.cc/rKxHD9DL)

6. **¡Preparado para recibir commits!**
   - En este punto, Jenkins responderá automáticamente a los commits en tu repositorio.
   - (https://postimg.cc/47X9JWkx) 

### Verificación del Funcionamiento:

- Para verificar su funcionamiento y completar la documentación de este README, se realizaron múltiples cambios en la rama principal, que fueron recibidos exitosamente por el proceso de Entrega Continua (CD).
  - Proceso finalizado de buil: (https://postimg.cc/239N735H) 
  - Logs que muestra que se lanzao la tarea (https://postimg.cc/rRL31YsL) 

## Diagrama de Alto Nivel de la preparación del CI/CD
---

[![asfasffffffffffffffffffffffffffffffffffffffffffffffff.png](https://i.postimg.cc/K81882Vx/asfasffffffffffffffffffffffffffffffffffffffffffffffff.png)](https://postimg.cc/Mn8S9hqF)
