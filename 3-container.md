# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name srv-web nginx:alpine
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

```
docker create hello-world
```

Crear el contenedor usando la imagen hello-world

### Listar los contenedores ejecutándose o no

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start srv-web
```
Iniciar el contenedor srv-web 

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep srv-web2
```

### Para detener un contenedor

```
docker stop srv-web2
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name srv-web2 nginx:alpine
```
![Ecosistema de Docker](img/dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine

**¿Qué sucede luego de la ejecución del comando?**
Lo que sucede en la terminal queda "bloqueado", impdiendo ingresar nuevos comandos hasta que se detenga el contenedor.

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name srv-web3 nginx:alpine
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine

### Para eliminar un contenedor

```
docker rm 88bb3e91bc302ea7cc8b3aa6d7620f8473793657e2e12b7ebd6c560c40e1a541
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 

Verificar que el contenedor que se eliminó

```
docker ps
```

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f srv-web3
```
Eliminar el contenedor **srv-web3** 

Verificar que el contenedor que se eliminó

```
docker ps
```

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 

```
docker inspect srv-web
```
