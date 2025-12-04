# Practica Docker Hub

## Creacion del archivo
- Creo el directorio `.github\workflows\action.yml`

## Explicación del codigo

### Name
https://github.com/acasmor0802/2526_DAW_u2_springboot/blob/5a83cf1d482083c734457b0eca7acacc9c10b56e/.github/workflows/action.yml#L1
Pongo el nombre del workflow: `Docker Image`

### On
https://github.com/acasmor0802/2526_DAW_u2_springboot/blob/5a83cf1d482083c734457b0eca7acacc9c10b56e/.github/workflows/action.yml#L2-L5
Cuándo se ejecutas el workflow:
- `push`: Al hacer push a la rama `master`
- `workflow_dispatch`: De forma manual en GitHub Actions

### Jobs
https://github.com/acasmor0802/2526_DAW_u2_springboot/blob/5a83cf1d482083c734457b0eca7acacc9c10b56e/.github/workflows/action.yml#L7-L9
Se ejecuta en `ubuntu-latest`

**Steps**:
https://github.com/acasmor0802/2526_DAW_u2_springboot/blob/5a83cf1d482083c734457b0eca7acacc9c10b56e/.github/workflows/action.yml#L12-L13
1. **Checkout repositorio**: Se descarga el código con `actions/checkout@v3`
https://github.com/acasmor0802/2526_DAW_u2_springboot/blob/5a83cf1d482083c734457b0eca7acacc9c10b56e/.github/workflows/action.yml#L15-L19
2. **Log en Docker Hub**: Despues autentifica usando `docker/login-action@v3` con los secrets `DOCKER_USERNAME` y `DOCKER_TOKEN`
https://github.com/acasmor0802/2526_DAW_u2_springboot/blob/5a83cf1d482083c734457b0eca7acacc9c10b56e/.github/workflows/action.yml#L21-L27
3. **Construccion y Push**: Construye y sube la imagen con `docker/build-push-action@v5`

## Configuración de Secrets
En **Settings -> Secrets and variables -> Actions** del repositorio, añadir:
- `DOCKER_USERNAME`: Usuario de Docker Hub
- `DOCKER_TOKEN`: Token de acceso

# DONDE ME HE QUEDADO
- No he podido logearme en docker hub y no implemente la funcion de poner el nombre en el titulo 
