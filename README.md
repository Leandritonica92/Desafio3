#                                                                            **DESAFIO 3**
---
## Objetivos del desafío: El objetivo de este desafío será crear algunos servicios básicos en nuestra cuenta de AWS e interactuar con ellos. Primero tendremos que verificar los prerrequisitos, en caso de ya cumplirlos, aclararlo en el instructivo. Luego crearemos una instancia EC2, un bucket S3 y un volumen de EBS:

1. **_Creación del usuario IAM:_**
   - Crearemos el usuario siguiendo los siguientes pasos:
   
      - **- Paso 1:**
        ![Paso 1](https://i.postimg.cc/W3XcHvRv/1.png)
   
      - **- Paso 2:**
        ![Paso 2](https://i.postimg.cc/MZ380qb0/2.png)
  
      - **- Paso 3:**
        ![Paso 3](https://postimg.cc/GTpxByQc)
   
      - **- Paso 4:**
        ![Paso 4](https://i.postimg.cc/tRWMJbvC/4.png)
   
      - **- Paso 5:**
        ![Paso 5](https://i.postimg.cc/R02gCpcH/5.png)

      - **- Paso 6:**
        ![Paso 6](https://i.postimg.cc/KcP0FN41/7.png)


2. **_Lanzar instancias en EC2:_**

   Para lanzar una instancia en EC2 es importante tener en cuenta la región o zona en la que se lanzará, en nuestro caso lo haremos en us-east-1 (N. Virginia) En la barra de búsqueda escribimos EC2 y vamos a Lanzar instancias.

      - **- Paso 1:**
        ![Paso 1](https://i.postimg.cc/JznxNCxX/9.png)

      - **- Paso 2:**
        ![Paso 2](https://i.postimg.cc/52R3pKKR/10.png)

      - **- Paso 5:**
        ![Paso 5](https://i.postimg.cc/JzG3yc7c/11.png)

      - **- Paso 6:**
        ![Paso 6](https://i.postimg.cc/L8wtjYnd/12.png)

      - **- Paso 8:**
        ![Paso 8](https://i.postimg.cc/63NC1krY/13.png)

      - **- Paso 9:**
        ![Paso 9](https://i.postimg.cc/Hn65njfh/14.png)


3. **_Conectarse a la Instancia por SSH desde nuestra VM:_**

   Hay varias formas para conectarnos a la instancia en esta ocasión lo haremos por medio de conexión SSH desde nuestra terminal de Linux 

      - **- Paso 1:**
        ![Paso 1](https://i.postimg.cc/ryj5QYKN/15.png)

      - **- Paso 2:**
        ![Paso 2](https://i.postimg.cc/1zDq6vk6/19.png)

      - **- Paso 3:**
        ![Paso 3](https://i.postimg.cc/26mBx4Yt/21.png)


4. **_Crear un bucket en el servicio S3:_**

   Una vez logueados al usuario que creamos con los permisos de AmazonS3FullAccess podremos crear un bucket para almacenamiento.

      - **- Paso 1:**
        ![Paso 1](https://i.postimg.cc/nrhjypCY/22.png)

      - **- Paso 2:**
        ![Paso 2](https://i.postimg.cc/br5J4bXp/24.png)

      - **- Paso 3:**
        ![Paso 3](https://i.postimg.cc/hGMKHxx6/25.png)

      - **- Paso 4:**
        ![Paso 4](https://i.postimg.cc/xCh84MVY/26.png)

      - **- Paso 5:**
        ![Paso 5](https://i.postimg.cc/7hzh8hqz/27.png)

      - **- Paso 6:**
        ![Paso 6](https://i.postimg.cc/SN0jL6Gf/28.png)


5. **_Elastic Block Store (EBS):_**
 
   Crear un volumen de EBS y linkearlo a la instancia que creamos previamente. 

      - **- Paso 1:**
        ![Paso 1](https://i.postimg.cc/YCR9wJBd/29.png)

      - **- Paso 2:**
        ![Paso 2](https://i.postimg.cc/Y9GqY0GP/31.png)

      - **- Paso 3:**
        ![Paso 3](https://i.postimg.cc/Wz0NYy76/33.png)

      - **- Paso 4:**
        ![Paso 4](https://i.postimg.cc/Y2FCS4wG/34.png)

      - **- Paso 5:**
        ![Paso 5](https://i.postimg.cc/856NsYxQ/36.png)

      - **- Paso 6:**
        ![Paso 6](https://i.postimg.cc/nrfZmkts/37.png)

      - **- Paso 7:**
        ![Paso 7](https://i.postimg.cc/7h14n2xK/38.png)

      - **- Paso 8:**
        ![Paso 8](https://i.postimg.cc/fRRsYy1v/39.png)

      - **- Paso 9:**
        ![Paso 9](https://i.postimg.cc/2S0zthnJ/40.png)

