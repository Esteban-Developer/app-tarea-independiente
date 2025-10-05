# App Tarea Independiente

Este proyecto es una aplicación web simple (HTML estático) desplegada automáticamente mediante **Jenkins**, **Docker** y **GitHub**.

##  Descripción
La aplicación usa un contenedor **Nginx** que sirve un archivo `index.html` con un mensaje de “Hola Mundo desde Docker”.

El flujo **CI/CD** implementado realiza:
1. Checkout del código desde GitHub.
2. Construcción de la imagen Docker.
3. Ejecución de pruebas básicas del contenedor.
4. Publicación de la imagen en DockerHub.
5. Despliegue automático de la app en el puerto **8081**.

---

##  Requisitos previos
- Docker instalado y en ejecución.  
- Jenkins corriendo en contenedor con acceso a Docker (`/var/run/docker.sock` montado).  
- Repositorio en GitHub y DockerHub configurados.  

---

##  Pasos para ejecutar el Pipeline

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/Esteban-Developer/app-tarea-independiente.git
   cd app-tarea-independiente
Configurar las credenciales en Jenkins:

Crear credencial de tipo Username with password con:

ID: dockerhub

Username: esteban889

Password: (token o contraseña de DockerHub)

Crear un nuevo pipeline en Jenkins:

Elegir opción “Pipeline desde SCM”.

SCM: Git

URL del repositorio:
https://github.com/Esteban-Developer/app-tarea-independiente.git

Ejecutar el pipeline.
Jenkins realizará todas las etapas automáticamente:

Build Image → crea la imagen esteban889/app-tarea-independiente.

Run Tests → verifica el contenedor.

Push Image → sube la imagen a DockerHub.

Deploy to Test → levanta la app en el puerto 8081.

## Verificación del despliegue
Verifica que el contenedor esté corriendo:

bash
Copiar código
docker ps
Verifica el contenido desde el navegador o con curl:

bash
Copiar código
curl http://localhost:8081
Ver logs del contenedor:

bash
Copiar código
docker logs test-app
Ver la imagen publicada en DockerHub:

bash
Copiar código
docker pull esteban889/app-tarea-independiente:latest
## Dificultades enfrentadas
Permisos del contenedor Jenkins para ejecutar Docker (Permission denied).

Configuración del socket /var/run/docker.sock dentro del contenedor.

Instalación manual del cliente Docker dentro de Jenkins.

Reconstrucción completa del entorno para asegurar compatibilidad.

## Imagen en DockerHub
Disponible en: DockerHub - esteban889/app-tarea-independiente

## Autor
Esteban Murillo Gómez