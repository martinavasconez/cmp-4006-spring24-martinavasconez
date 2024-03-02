# Especificamos la imagen NGINX como imagen base
FROM nginx

# Copiamos el archivo de configuración personalizado NGINX 
COPY nginx.conf /etc/nginx/nginx.conf

# Copia un archivo html al directorio indicado
COPY index.html /usr/share/nginx/html/index.html

#Exponemos el puerto 8080 al mundo exterior
EXPOSE 8888

# Inicializar NGINX cuando el contenedor se inicie.
CMD ["nginx", "-g", "daemon off;"]

