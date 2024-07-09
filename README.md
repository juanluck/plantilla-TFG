# Guía para Gestionar un TFG de Informática en GitHub con Metodología Ágil

## 1. Configuración Inicial

1. **Crear un Repositorio en GitHub**:
   - Ve a GitHub y crea un nuevo repositorio para tu TFG. Ponle un nombre significativo y añade una descripción del proyecto.

2. **Estructura del Repositorio**:
   - **README.md**: Incluir una introducción al proyecto, objetivos y una breve descripción de la metodología ágil.
   - **docs/**: Carpeta para la documentación del proyecto.
   - **src/**: Carpeta para el código fuente.
   - **tests/**: Carpeta para los test unitarios.

## 2. Metodología Ágil

### A. Establecimiento de Milestones

1. **Definir Milestones**:
   - En la sección "Projects" o "Milestones" de GitHub, define las etapas clave del proyecto. Cada milestone puede representar un sprint en la metodología ágil.
   - Ejemplo de milestones:
     - **Milestone 1**: Análisis de Requisitos.
     - **Milestone 2**: Diseño de la Arquitectura.
     - **Milestone 3**: Implementación.
     - **Milestone 4**: Pruebas y Validación.
     - **Milestone 5**: Documentación Final y Presentación.

2. **Asignar Fechas Límite**:
   - Asigna fechas límite realistas a cada milestone para asegurar el progreso continuo.

### B. Definición de Tareas con Issues

1. **Crear Issues**:
   - Utiliza la sección de "Issues" para crear tareas específicas relacionadas con cada milestone.
   - Ejemplo de issues:
     - **Milestone 1**:
       - Issue 1: Recopilar requisitos del usuario.
       - Issue 2: Analizar requisitos y priorizarlos.
     - **Milestone 2**:
       - Issue 3: Diseñar la base de datos.
       - Issue 4: Crear diagramas de flujo.

2. **Etiquetas y Asignaciones**:
   - Etiqueta los issues según su naturaleza: `bug`, `enhancement`, `documentation`, `question`.
   - Asigna issues a ti mismo u otros colaboradores si hay más personas involucradas.

### C. Casos de Uso y Test Unitarios

1. **Definir Casos de Uso**:
   - Documenta los casos de uso en la carpeta `docs/`.
   - Cada caso de uso debe describir una funcionalidad específica desde la perspectiva del usuario.

2. **Desarrollar Test Unitarios**:
   - Escribe test unitarios para cada funcionalidad en la carpeta `tests/`.
   - Utiliza frameworks de pruebas como `JUnit` para Java, `pytest` para Python, etc.
   - Asegúrate de que cada test esté vinculado a un issue o caso de uso específico.

### D. Workflows

1. **Definir Workflows en GitHub Actions**:
   - Configura workflows en `.github/workflows/` para automatizar tareas como la ejecución de test unitarios y despliegues.
   - Ejemplo de workflow para ejecutar tests en cada push:
     ```yaml
     name: Run Tests

     on: [push, pull_request]

     jobs:
       build:
         runs-on: ubuntu-latest
         steps:
         - uses: actions/checkout@v2
         - name: Set up Python
           uses: actions/setup-python@v2
           with:
             python-version: '3.x'
         - name: Install dependencies
           run: |
             pip install -r requirements.txt
         - name: Run tests
           run: |
             pytest
     ```

## 3. Integración de la Documentación

1. **Mantener la Documentación Actualizada**:
   - Documenta cada etapa del proyecto en la carpeta `docs/`.
   - Utiliza Markdown para escribir documentos claros y estructurados.
   - Asegúrate de que el README.md ofrezca un índice de la documentación más detallada disponible en `docs/`.

2. **Documentación de APIs**:
   - Si desarrollas una API, utiliza herramientas como Swagger o Postman para generar y mantener la documentación de la API.

## 4. Interacción entre Elementos

1. **Milestones y Issues**:
   - Cada milestone agrupa varios issues. Al completar un issue, se avanza hacia el cumplimiento del milestone.
   - Usa la vinculación de issues a milestones para tener una visión clara del progreso.

2. **Issues y Casos de Uso**:
   - Los issues representan tareas específicas derivadas de los casos de uso documentados.
   - Cada issue debe referirse a un caso de uso para asegurar que todas las funcionalidades requeridas se implementen y prueben correctamente.

3. **Test Unitarios y Workflows**:
   - Los test unitarios aseguran que cada funcionalidad (definida por los casos de uso y documentada en issues) funciona correctamente.
   - Los workflows automatizan la ejecución de estos tests para asegurar calidad continua y detección temprana de errores.

## 5. Conclusión

Sigue estos pasos para organizar y gestionar tu TFG en GitHub de manera eficiente utilizando una metodología ágil. La clave está en mantener una documentación clara, realizar tareas de manera incremental y asegurar la calidad mediante pruebas automatizadas. ¡Buena suerte con tu proyecto!
