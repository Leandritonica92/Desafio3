#                                                                            **DESAFIO 3**
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

 https://postimg.cc/GTpxByQc

   Seleccionamos Crear usuario

- Paso 4.

  https://i.postimg.cc/tRWMJbvC/4.png

  En la casilla de “Nombre de usuario” le asignaremos un nombre de usuario y seleccionaremos los siguientes parámetros: 
  - Proporcione acceso de usuario a la consola de administración de AWS: opcional
  - Quiero crear un usuario de IAM
  -Contraseña personalizada


- Paso 5.

  En este paso le daremos los permisos al usuario en caso que ya se tengan un grupo creado se lo asignaremos. En nuestro caso crearemos uno nuevo. 
  para los cual vamos al botón “Crear un grupo”


  https://i.postimg.cc/R02gCpcH/5.png


 Le asignamos un nombre, buscamos y le asignaremos los siguientes permisos: 
 - AmazonEC2FullAccess 
 - AmazonS3FullAccess 
 - AmazonEBSCSIDriverPolicy
 - ROSAAmazonEBSCSIDriverOperatorPolicy

 https://i.postimg.cc/KcP0FN41/7.png


- Paso 6. 

 Agregarles las Tags

 https://i.postimg.cc/Hs338kwH/8.png


2. **Lanzar instancias en EC2**

 Para lanzar una instancia en EC2 es importante tener en cuenta la región o zona en la que se lanzará, en nuestro caso lo haremos en us-east-1 (N. Virginia) En la barra de búsqueda escribimos EC2 y vamos a Lanzar instancias.

- Paso 1

 https://i.postimg.cc/JznxNCxX/9.png


- Paso 2. 

 Elegir un nombre para nuestra instancia y buscamos el recurso o la AMI. Elegimos el tipo de instancia t2.micro que está dentro del Free Tier.

  https://i.postimg.cc/52R3pKKR/10.png


- Paso 5. 
 Creamos un par de claves de inicio (Este Key Pair lo podemos utilizar en cualquier máquina desplegada en la región de Virginia)

 https://i.postimg.cc/JzG3yc7c/11.png

- Paso 6. 

   Configuramos los parámetros de Red 
 - Predeterminado Crear grupo de Seguridad 
 - Permitir el tráfico SSH (Dejarlo en Anywhere es una mala práctica porque permitiría que haya conexión de cualquier lugar) de momento lo dejaremos así
 - Permitir el trafico de HTTPS desde internet
 - Permitir el trafico de HTTP desde internet


 https://i.postimg.cc/L8wtjYnd/12.png


- Paso 8

 Instalamos Apache2 desde nuestra Instancia de la siguiente manera En 
 Detalles avanzados escribiremos el siguiente script

 https://i.postimg.cc/63NC1krY/13.png

- Paso 9

 Lanzar instancia
 En la sección de Instancia podemos verificar que la instancia creada está corriendo

https://i.postimg.cc/Hn65njfh/14.png


**Conectarse a la Instancia por SSH desde nuestra VM**


 Hay varias formas para conectarnos a la instancia en esta ocasión lo haremos por medio de conexión SSH desde nuestra terminal de Linux 

- Paso 1

 Copiamos nuestra clave codificada o KeyPair en algún fichero en nuestra VM una vez en ese directorio corremos el comando chmod 400 para darle permisos y luego corremos el comando ssh -i + el contenido de nuestro archivo. pem

https://i.postimg.cc/ryj5QYKN/15.png

 Una vez que ingresamos a nuestra terminal, le damos permisos a la clave previamente descargada “clavedesafio3.pem” y siguiente a eso el ejemplo que nos brinda aws para conectarnos a nuestra instancia de aws

 https://i.postimg.cc/sD2789Wd/16.png

 Si todo esta correctamente bien realizado vamos a recibir una bienvenida una vez ingresado a la instancia de aws y podemos corroborar que estamos dentro comparando la ip publica de la instancia de aws dentro del dashboard de la plataforma con el nombre de usuario en la terminal del Linux

 
 https://i.postimg.cc/3JbmH4jy/17.png


 https://i.postimg.cc/K8kLcGQ0/18.png

- Paso 2
  Verificamos si el servidor Apache2 fue instalado con el comando: sudo systemctl status apache2

  https://i.postimg.cc/1zDq6vk6/19.png

- Paso 3

 Verificar en un navegador Para verificar que podemos navegar en el servidor lo hacemos con la dirección IP Pública de nuestra Instancia

 https://i.postimg.cc/K8kLcGQ0/18.png

 Copiamos la dirección en la barra de navegación y nos abrirá el servidor.

 https://i.postimg.cc/26mBx4Yt/21.png


 **Crear un bucket en el servicio S3**


 Una vez logueados al usuario que creamos con los permisos de AmazonS3FullAccess podremos crear un bucket para almacenamiento.


- Paso 1.

 Ingresamos un nombre para el bucket y dejamos todos los servicios predeterminados, por último, cliqueamos en el botón Crear Bucket.


 https://i.postimg.cc/nrhjypCY/22.png


https://i.postimg.cc/nrSjZgm8/23.png


- Paso 2
  
 Subir un archivo al bucket Una vez creado el bucket listamos e ingresamos al bucket haciendo clic sobre el bucket.


 https://i.postimg.cc/br5J4bXp/24.png


- Paso 3

 Cargar o subir el archivo


 https://i.postimg.cc/hGMKHxx6/25.png

- Paso 4: 

 Configuramos la política del objeto dentro del bucket para poder acceder al recurso a través de internet


 https://i.postimg.cc/xCh84MVY/26.png


- Paso 5:
 
 Dentro del dashboard del buckets3 podemos obtener la url del objeto, la que nos va a permitir acceder al recurso a través de internet.


 https://i.postimg.cc/7hzh8hqz/27.png

- Paso 6

  Verificamos que podemos ver con el link correspondiente el objeto dentro del bucket del S3


https://i.postimg.cc/SN0jL6Gf/28.png



**Elastic Block Store (EBS)**
 

Crear un volumen de EBS y linkearlo a la instancia que creamos previamente. 

- Paso 1

 En el panel del servicio EC2 nos dirigimos al apartado Elastic Block Store (EBS), Volúmenes damos click al botón Crear Volumen. 

 Le asignaremos un tamaño, para este ejercicio le asignamos un espacio de 3 GB ponemos cuidado que este en la misma zona de disponibilidad que nuestra instancia EC2 es decir us-east-1a.

 Ciframos el volumen y por último Creamos el Volumen


 https://i.postimg.cc/YCR9wJBd/29.png


 https://i.postimg.cc/XvvvNQV4/30.png

- Paso 2.

 Asociar el Volumen Una vez creado el volumen en el panel principal de volúmenes lo seleccionamos y dentro de Acciones hacemos clic en la opción Asociar Volumen.


https://i.postimg.cc/Y9GqY0GP/31.png


https://i.postimg.cc/Y95237QC/32.png


Por último, le damos clic en el botón Asociar Volumen.


- Paso 3.
  Listar nuestras unidades Nos conectamos a la instancia por el método que hayamos elegido en mi caso lo hice por SSH y listamos nuestras unidades con el siguiente comando lsblk


 https://i.postimg.cc/Wz0NYy76/33.png


- Paso 4. 
 Formatear el volumen EBS Formateamos el volumen con el siguiente comando: sudo mkfs -t ext4 /dev/xvdf (/xvdf corresponde al volumen que le asignamos en el paso No. 2)


 https://i.postimg.cc/Y2FCS4wG/34.png


 Verificamos nuevamente con el comando lsblk -f 

 
 https://i.postimg.cc/VLcL0YY7/35.png


- Paso 5

 Crear el directorio /desafíos sudo mkdir /desafios Paso 6. Agregar el volumen al archivo FSTAB nano /etc/fstab (también podemos usar vim)


 https://i.postimg.cc/856NsYxQ/36.png


- Paso 7. 
 Montar el disco sudo mount -a 

 https://i.postimg.cc/nrfZmkts/37.png


- Paso 8.

Verificó que el volumen se haya montado lsblk -f


https://i.postimg.cc/7h14n2xK/38.png


- Paso 9

 Descargar el fichero ActividadDesafioAWS.pdf de nuestro Bucket con el comando wget


 https://i.postimg.cc/fRRsYy1v/39.png


 https://i.postimg.cc/2S0zthnJ/40.png


https://i.postimg.cc/CKWVyN5v/41.png
