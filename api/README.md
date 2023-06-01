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