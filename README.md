# Docker

Proceso detallado de la creación de contenedor e imagen en Docker

## Proceso

Lo primero es logearse mediante el terminal, luego se crea un Dockerfile que contiene la build que vamos a subir como imagen para luego arrancarla mediante el mismo terminal. Por último se edita el index para mostrar un mensaje personalizado y se crea y monta un volumen para ese contenedor

### Comandos

Los comandos están enfocados a mi directorio en el momento de hacerlo, pero lo ideal es crear una carpeta docker donde nos movamos con el terminal para ejecutar todo desde el directorio acutal

* Iniciar sesión: `docker login -u {usuario}`
* Subir dockerfile con la imagen: `docker build .`
* Arrancar la imagen e indicar el puerto para el localhost: `docker run -dp 8080:80 httpd:latest`
* Comprobamos los contenedores activos: `docker ps`
* Editar index: Añadimos la siguiente etiqueta al dockerfile `ADD index.html /usr/local/apache2/htdocs/` de forma que se sube el index.html de la carpeta actual al apache donde se encuentra el contenedor
* Creamos el volumen: `docker volume create mi-vol`
* Asignamos el volumen al contenedor: `docker run -v mi-vol:/opt/data`
* Comprobamos que se ha asignado: `docker inspect mi_container`
* Podemos acceder al terminal de la VM con: `docker exec -it ID_CONTENEDOR bash` y dirigirnos con un cd a la carpeta htdocs donde se encuentra el index.html

## ¿Qué he aprendido?

He aprendido a montar una imagen personalizada básica en un contenedor de Docker, asignarle un volumen y editar el index para que muestre un mensaje personalizado

### Comandos aprendidos

Los siguientes comandos, indicando los parámetros al final de cada uno, han sido suficientes para hacer este proyecto y comprobar que todo iba bien

* `docker login`
* `docker build`
* `docker inspect`
* `docker run -d`
* `docker ps`
* `docker volume create`
* `docker run -v`


## Herramientas

* Docker desktop
* VS Code
* MobaXterm
