
`docker --version` permite ver la version de docker

`docker images` permite ver las imagenes

`docker run` permite crear un contenedor

ejemplo de contenedor basico:

```docker 
docker run --name mysqlv1 -e MYSQL_ROOT_PASSWORD=123456 -d mysql:latest
```

`docker contrainer ps` permite visualizar los contenedores que estan en ejecucion

`docker ps -a` permite visualizar todos los contenedores en ejecucion o no

`docker stop id o nombre del contenedor` detiene un contenedor

`docker start id o nombre del contenedor ` inicia un contenedor

`docker rm o id o el nombre del contenedor` eliminar contenedor - pero se debe detner primero el contenedor

`docker rm -f id o el nombre del contenedor` forza la eliminacion del contenedor sin reiniciarlo