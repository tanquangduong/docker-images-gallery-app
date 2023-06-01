# Docker Project

Project for the **Dockerfiles** and **Docker Compose** sections

## Initial configuration

- Create account at the https://unsplash.com
- At the https://unsplash.com/oauth/applications create new **demo** application with title **"Images Gallery"**.
  Demo applications are limited to 50 requests per hour
- In the newly created application find section **"Keys"** and copy **Access Key**
- In the **api** folder create file **.env.local** and add there following line:

```
UNSPLASH_KEY=<Paste copied Access Key here>
```

**EXAMPLE** with fake code(don't try to use it in your app):

```
UNSPLASH_KEY=2MJvApIkV13hfg2LmQlneILfHoJ2ttlzSdPKefGOyKM
```

- Save modified **.env.local** file

# Run both frontend and backend api using their image
```
docker run -p 5050:5050 -d images-gallery-api
docker run -p 3000:3000 -d images-gallery-frontend

# see runing containers
docker ps

# stop and start container
docker stop CONTARINER_NAME
docker start CONTARINER_NAME

# logs containers
docker logs CONTARINER_NAME
```

# Docker-compose
```
docker-compose up

# run in backgroud
docker-compose up -d

# stop both containers simutaniously 
docker-compose down

```

# Access mongo shell
```
docker exec -it docker-images-gallery-app-mongo-1 mongosh --username root --password very-strong-db-password
show dbs
use admin
show collections
```