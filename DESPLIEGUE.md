# Practica Docker Hub

## Creacion del archivo
- Creo el directorio `.github\workflows\action.yml`

## Explicación del codigo

### Name
Pongo el nombre del workflow: `Docker Image`

### On
Cuándo se ejecutas el workflow:
- `push`: Al hacer push a la rama `master`
- `workflow_dispatch`: De forma manual en GitHub Actions

### Jobs
Se ejecuta en `ubuntu-latest`

**Steps**:
1. **Checkout repositorio**: Se descarga el código con `actions/checkout@v3`
2. **Log en Docker Hub**: Despues autentifica usando `docker/login-action@v3` con los secrets `DOCKER_USERNAME` y `DOCKER_TOKEN`
3. **Construccion y Push**: Construye y sube la imagen con `docker/build-push-action@v5`

## Configuración de Secrets
En **Settings -> Secrets and variables -> Actions** del repositorio, añadir:
- `DOCKER_USERNAME`: Usuario de Docker Hub
- `DOCKER_TOKEN`: Token de acceso

# DONDE ME HE QUEDADO
- No he podido logearme en docker hub y no implemente la funcion de poner el nombre en el titulo 
