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

- Build custom image 
```
docker build . -t images-gallery-api
```
- Run our custom image
```
docker run -p 5050:5050 images-gallery-api # first 5050 is our local port, second 5050 is the port inside our containter
# see our containers
docker ps
docker ps -a

```
- Test api run con our runing container: http://localhost:5050/new-image?query=car

- Go inside the runing container to see the structure
```
# get container name
docker ps
# go inside the runing container
docker exec -it CONTAINER_NAME bash # 'i' stands for interactive and 't' stands for terminal
# see runing process
ps -x
# exit
exit
```