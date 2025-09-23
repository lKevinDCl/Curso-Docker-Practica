# Bind VOlumes:

> cd nest-graphql-app
> docker pull 16-alpine3.16

docker run --name nest-app -w /app -p 80:3000 -v %cd%:/app node:16-alpine3.16 sh -c "yarn install && yarn start:dev"


