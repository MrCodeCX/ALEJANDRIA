Docker Engine instalado

docker run -i -t image < command>

docker create --name < name> < container>
docker start < container>
docker exec -i -t image < command>
docker stop < container>

docker ps
docker ps -a

docker images
docker pull < image>

Sobre los contenedores y sus permisos, todos los permisos se definen en exec

Para tener acceso a interfaz grafica usar primero
xhost +local:docker               
Y en cada acceso
docker exec -it -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix tu_contenedor zsh

---
### LECTURES
- https://docs.docker.com/engine/install/ubuntu/
