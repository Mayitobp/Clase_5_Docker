# Clase_5_Docker
crear contenedor con una imagen de docker basada en nginx, utulizando docker-compose

Primeramente creamos un directorio con el comando MKDIR dentro del cual vamos a crear el dockerfile de la imagen personalizada q deseamos contruir en mi caso fue:
mkdir /compose-demo
Una vez dentro creamos el archivo dokcerfile ---- "sudo touch Dockerfile" y lo editamos con el comando "nano"
Como lo q se pedía era implementar una imagen de docker basada en Nginx pero personalizada con un ".html", el cuerpo del Dockerfile quedaría de la sig manera:
          FROM nginx:alphine
          COPY index.html /usr/share/nginx/html/
          EXPOSE 80
          CMD ["nginx", "-g", "daemon off;"]
DONDE:
    FROM	-Indica la imagen base sobre la que se basa esta imagen
    COPY	-Copia un archivo del build context y lo guarda en la ruta donde se encuentra el           html de Nginx
    EXPOSE -Indicamos que este contenedor se comunica por el puerto 80/tcp
    CMD -para ejecutar lo q se indica dentro [] una vez q inicia nuestro contenedor
Una vez estando en el directorio del Dockerfile , ejecutamos el comando para crear y levantar nuestra propia imagen----[docker build -t "image's namem" .]
 
Luego es necesario crear y personalizar nuestro index.html y finalmente elaborar nuestro docker-compose para levantar nuestro contenedor con esa imagen, definir un volumen para persisitir el fichero entre otras configuraciones.
