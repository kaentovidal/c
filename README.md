# Plantilla FullStack

En este proeto esta implementado Docker y se puede trabajar independientemente sobre el backend y el fronted

## Comando útiles para el backend
### Inicializando el back
Nos alojamos en el directorio backend y lo inicializamos
```sh
cd /backend
npm init
```
Instalamos las dependencias requeridas
```sh
npm i express prisma @prisma/client
```
 

* `prisma`: es un ORM para interactuar con la base de datos. En este caso interactuara con el contendor de postgres lo cual si lo usamos adecuadamente nos simplificara el desarrollo.
  * Inicializamos Prisma:
  `npx prisma init`

Creamos en archivo `.env` para trabajar con las variables de entorno `touch .env` e insertamos lo siguiente: `DATABASE_URL="postgresql://postgres:postgres@localhost:5432/postgres?schema=public"` 


### compilamos el contenedor 

`docker compose build backend`

* Para levantar los contenedor con la base de datos
```sh
docker compose up -d backend
docker compose up -d db
```

Para migrar las configuaciones del backend con prisma a al contendor con postgres
```
docker exec -it backend npx prisma migrate dev --name init
```
## Comandos utiles para el frontend
### Inicializando el front
Nos alojamos en el directorio /frontend y lo inicializamos
```sh
cd /frontend
npm init
```
Instalamos las dependencias requeridas
```sh
npm i express prisma @prisma/client
```
 


