# Crear la red conjunto con el contenedor

> docker run -d --name world-db -p 3311:3306 -e MARIADB_USER=example-user -e MARIADB_PASSWORD=user-password -e MARIADB_ROOT_PASSWORD=root-secret-password -e MARIADB_DATABASE=world-db -v world-db:/var/lib/mysql -network world-app mariadb:jammy

>docker container run --name phpmyadmin -d -e PMA_ARBITRARY=1 -p 8080:80 -network world-app phpmyadmin:5.2.0-apache
