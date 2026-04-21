# BIND MOUNT
En un bind mount mapeamos (montar) un directorio o archivo específico del sistema de archivos del host con una parte del sistema de ficheros del contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen> 
```
ó
```
docker run -d --name <nombre contenedor> --mount type=bind,source=<ruta carpeta host>,target=<ruta carpeta contenedor> <imagen>
```
- destination, dst, target: La ruta donde se monta el archivo o directorio en el contenedor.
- source, src: El origen del montaje.
  
### En tu computador crear una carpeta llamada nginx y dentro de esta carpeta crea otra llamada html. Como se aprecia en la figura.
![Volúmenes](directorio.PNG)

### Crear un contenedor con la imagen nginx:alpine, mapear todos por puertos, para la ruta carpeta host colocar el directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html (esta ruta se obtiene al revisar la documentación de la imagen)
![Volúmenes](volumen-host.PNG)
# COMPLETAR CON EL COMANDO

### ¿Qué sucede al ingresar al servidor de nginx?
```
Se observa un error 403 Forbidden.
```

### ¿Qué pasa con el archivo index.html del contenedor?
```
El archivo index.html original que venía dentro de la imagen de Nginx queda oculto o enmascarado.
```

### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de tu computador en la carpeta html
### ¿Qué sucede al ingresar al servidor de nginx?
```
El servidor ahora mostrará correctamente la página web del template descargado.
```

### Eliminar el contenedor
```
docker rm servidor-web
```

### ¿Qué sucede al crear nuevamente un contenedor montado al directorio definidos anteriormente?
```
Al crear el nuevo contenedor, el sitio web aparecerá funcionando perfectamente desde el primer segundo. A diferencia de lo que pasaría si los archivos estuvieran dentro del contenedor, aquí los datos son persistentes porque residen en el host.
```


