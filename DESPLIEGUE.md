# Documentación de GitHub Actions

## Configuración del Workflow

### 1. Ubicación del archivo
Crear el archivo `.github/workflows/action.yml` en la raíz del proyecto.

### 2. Estructura básica
- **name**: Nombre del workflow `Docker Image`
- **on**:Para ejecutar el workflow (push a master o manualmente)
- **jobs**: Define las tareas a ejecutar

### 3. Pasos del workflow

El workflow ejecuta los siguientes pasos automáticamente:

1. **Checkout**: Descarga el código del repositorio
2. **Setup JDK 17**: Configura Java 17 para compilar
3. **Build Gradle**: Genera el archivo WAR con `./gradlew bootWar`
4. **Login Docker Hub**: Autentica con Docker Hub usando secrets
5. **Build & Push**: Construye la imagen Docker y la sube a Docker Hub con dos tags:
   - `latest`: Última versión
   - `{commit-sha}`: Versión específica del commit

### 4. Configuración de Secrets en GitHub

Para que funcione, debes configurar estos secrets en el repositorio:

1. Ve a: **Settings -> Secrets -> and variables -> Actions -> New repository secret**
2. Añade los siguientes secrets:
   - `DOCKER_USERNAME`: Tu usuario de Docker Hub
   - `DOCKER_TOKEN`: Token de acceso generado en Docker Hub 

### 5. Ejecución

El workflow se ejecuta automáticamente en cada push a `master` o manualmente desde la pestaña Actions en GitHub 