#Dependencias de desarrollo
FROM node:19.2-alpine3.16 as deps
WORKDIR  /app
COPY package.json ./
RUN npm install

# Builder y Test
FROM node:19.2-alpine3.16 as builder
WORKDIR /app
COPY --from=deps /app/node_modules ./node_modules
COPY . .
RUN npm run test

#Dependencias de producción
FROM node:19.2-alpine3.16 as prod-deps
WORKDIR /app
COPY package.json ./
RUN npm install --prod

# Runnner
FROM node:19.2-alpine3.16 as Runnner
WORKDIR /app
COPY --from=deps /app/node_modules ./node_modules
COPY app.js ./
COPY task/ ./tasks
CMD [ "node", "app.js" ]
