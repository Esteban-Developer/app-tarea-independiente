# App Tarea Independiente

Este proyecto es una aplicación web simple (HTML estático) desplegada automáticamente mediante **Jenkins**, **Docker** y **GitHub**.

##  Descripción
La aplicación usa un contenedor Nginx que sirve un archivo `index.html` con un mensaje de “Hola Mundo desde Docker”.

El flujo CI/CD realiza:
1. Checkout del código desde GitHub.
2. Construcción de la imagen Docker.
3. Pruebas básicas del contenedor.
4. Publicación de la imagen en DockerHub.
5. Despliegue de la app en el puerto **8081**.

##  Imagen en DockerHub
Disponible en: [DockerHub - esteban889/app-tarea-independiente](https://hub.docker.com/r/esteban889/app-tarea-independiente)

##  Autor
**Esteban Murillo Gómez**
