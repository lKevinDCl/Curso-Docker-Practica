# PHPMYADMIN

> Descargar imagen de phmyadmin:
>> docker pull phpmyadmin:5.2.0-apache

>> Consola devolvio:

5.2.0-apache: Pulling from library/phpmyadmin
45244a9928d1: Pulling fs layer
0b85949bbffa: Pulling fs layer
d25586855c63: Pulling fs layer
1de46a46cfcd: Pulling fs layer
ed7aad4fc2fb: Pulling fs layer
0c7c6d5ce997: Pulling fs layer
9195cab71d03: Pulling fs layer
d22a5530765a: Pulling fs layer                                                                                              
0b85949bbffa: Pull complete
ed7aad4fc2fb: Pull complete
0c7c6d5ce997: Pull complete
9195cab71d03: Pull complete
d22a5530765a: Pull complete
9eaa1559de60: Pull complete
96e5415e261a: Pull complete
e98ea42e90a6: Pull complete
139d4815e950: Pull complete
dc59c4386191: Pull complete
9cc46e699e97: Pull complete
9a420fd884ad: Pull complete
01b5b2efb836: Pull complete
9a8d67ebc9db: Pull complete
1ff2782a8ae8: Pull complete
Digest: sha256:7c8751488b72255047bdc38ea1e9bf6b33b163a3c15ae276b2ac3c1a633a53c6
Status: Downloaded newer image for phpmyadmin:5.2.0-apache
docker.io/library/phpmyadmin:5.2.0-apache


## Usar phpmyadmin

> docker container run --name phpmyadmin -d -e PMA_ARBITRARY=1 -p 8080:80 phpmyadmin:5.2.0-apache

>> consola devolvio:
in:5.2.0-apache
Unable to find image 'phpmyadmin:5.2.0-apache' locally
5.2.0-apache: Pulling from library/phpmyadmin
139d4815e950: Pulling fs layer
e98ea42e90a6: Pulling fs layer
9eaa1559de60: Pulling fs layer
96e5415e261a: Pull complete
1ff2782a8ae8: Pull complete
1de46a46cfcd: Pull complete
ed7aad4fc2fb: Pull complete
d25586855c63: Pull complete
9a8d67ebc9db: Pull complete
9195cab71d03: Pull complete
45244a9928d1: Pull complete
9a420fd884ad: Pull complete
dc59c4386191: Pull complete
0c7c6d5ce997: Pull complete
01b5b2efb836: Pull complete
d22a5530765a: Pull complete
9cc46e699e97: Pull complete
0b85949bbffa: Pull complete
Digest: sha256:7c8751488b72255047bdc38ea1e9bf6b33b163a3c15ae276b2ac3c1a633a53c6
Status: Downloaded newer image for phpmyadmin:5.2.0-apache

> contenedor:
3f0d05256bb5d5d5dcd7d68024f4aaac6defcfe48b617a8c50cd72886298f1ef

## Servicio de phpmyadmin docker container

![alt text](screenshots-Lesson-2/image8.png)


## Intento 1 de Inicio de sesion:

![alt text](screenshots-Lesson-2/image9.png)

> No va  a poder iniciar sesion debido a que el servicio expuesto no se encuentra en la misma red

