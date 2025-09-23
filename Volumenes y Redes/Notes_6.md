# Bind Volumes:

> cd nest-graphql-app
> docker pull 16-alpine3.16

docker run --name nest-app -w /app -p 80:3000 -v %cd%:/app node:16-alpine3.16 sh -c "yarn install && yarn start:dev"

> Permite poder trabajar en un entorno de desarrollo con contenedores de linux, mac o windows.
>> es mas lento que hacerlo de manera local, pero permite no necesitar de maquinas virtuales


