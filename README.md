#                                                                            **DESAFIO 3**
---
## Objetivos del desafío: 
El objetivo de este desafío será crear algunos servicios básicos en nuestra cuenta de AWS e interactuar con ellos. Primero tendremos que verificar los prerrequisitos, en caso de ya cumplirlos, aclararlo en el instructivo. Luego crearemos una instancia EC2, un bucket S3 y un volumen de EBS:

1. **_Creación del usuario IAM:_**
   - Crearemos el usuario siguiendo los siguientes pasos:

      - Paso 1

        ![Paso 1](https://i.postimg.cc/W3XcHvRv/1.png)

   - Buscamos el recurso en la barra de búsqueda de la plataforma con las palabras AIM y seleccionamos el recurso. 

      - Paso 2:

        ![Paso 2](https://i.postimg.cc/MZ380qb0/2.png)

   - Buscamos Usuarios y le damos click

      - Paso 3.

        ![Paso 3](https://postimg.cc/GTpxByQc)

   - Seleccionamos Crear usuario

      - Paso 4.

        ![Paso 4](https://i.postimg.cc/tRWMJbvC/4.png)

        En la casilla de “Nombre de usuario” le asignaremos un nombre de usuario y seleccionaremos los siguientes parámetros: 
        - Proporcione acceso de usuario a la consola de administración de AWS: opcional
        - Quiero crear un usuario de IAM
        - Contraseña personalizada


      - Paso 5.

        En este paso le daremos los permisos al usuario en caso que ya se tengan un grupo creado se lo asignaremos. En nuestro caso crearemos uno nuevo. 
        para los cual vamos al botón “Crear un grupo”

        ![Paso 5](https://i.postimg.cc/R02gCpcH/5.png)

        Le asignamos un nombre, buscamos y le asignaremos los siguientes permisos: 
        - AmazonEC2FullAccess 
        - AmazonS3FullAccess 
        - AmazonEBSCSIDriverPolicy
        - ROSAAmazonEBSCSIDriverOperatorPolicy

        ![Paso 6](https://i.postimg.cc/KcP0FN41/7.png)

   - Paso 6. 
      Agregarles las Tags

        ![Paso 6](https://i.postimg.cc/Hs338kwH/8.png)


2. **_Lanzar instancias en EC2:_**

   Para lanzar una instancia en EC2 es importante tener en cuenta la región o zona en la que se lanzará, en nuestro caso lo haremos en us-east-1 (N. Virginia) En la barra de búsqueda escribimos EC2 y vamos a Lanzar instancias.

      - Paso 1

        ![Paso 1](https://i.postimg.cc/JznxNCxX/9.png)

      - Paso 2. 

        Elegir un nombre para nuestra instancia y buscamos el recurso o la AMI. Elegimos el tipo de instancia t2.micro que está dentro del Free Tier.

        ![Paso 2](https://i.postimg.cc/52R3pKKR/10.png)

      - Paso 5. 
        Creamos un par de claves de inicio (Este Key Pair lo podemos utilizar en cualquier máquina desplegada en la región de Virginia)

        ![Paso 5](https://i.postimg.cc/JzG3yc7c/11.png)

      - Paso 6. 

        Configuramos los parámetros de Red 
        - Predeterminado Crear grupo de Seguridad 
        - Permitir el tráfico SSH (Dejarlo en Anywhere es una mala práctica porque permitiría que haya conexión de cualquier lugar) de momento lo dejaremos así
        - Permitir el tráfico de HTTPS desde internet
        - Permitir el tráfico de HTTP desde internet

        ![Paso 6](https://i.postimg.cc/L8wtjYnd/12.png)

      - Paso 8

        Instalamos Apache2 desde nuestra Instancia de la siguiente manera En 
        Detalles avanzados escribiremos el siguiente script

        ![Paso 8](https://i.postimg.cc/63NC1krY/13.png)

      - Paso 9

        Lanzar instancia
        En la sección de Instancia podemos verificar que la instancia creada está corriendo

        ![Paso 9](https://i.postimg.cc/Hn65njfh/14.png)


**_Conectarse a la Instancia por SSH desde nuestra VM_**

   Hay varias formas para conectarnos a la instancia en esta ocasión lo haremos por medio de conexión SSH desde nuestra terminal de Linux 

      - Paso 1

        Copiamos nuestra clave codificada o KeyPair en algún fichero en nuestra VM una vez en ese directorio corremos el comando chmod 400 para darle permisos y luego corremos el comando ssh -i + el contenido de nuestro archivo. pem

        ![Paso 1](https://i.postimg.cc/ryj5QYKN/15.png)

        Una vez que ingresamos a
