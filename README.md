# Hello Stages (Node.js, Git & Docker)
Proyecto integrador correspondiente al Trabajo Práctico de la asignatura **Gestión de Desarrollos de Software** (Tecnicatura Superior en Desarrollo de Software - UTN FRTDF). 
El proyecto consiste en una aplicación Node.js reproducible que implementa un flujo completo de Git y contenedores multi-stage con Docker Compose.

---

## Tecnologías Utilizadas
* **Node.js** (v24 LTS)
* **npm** (Node Package Manager)
* **Git** y **GitHub/GitLab**
* **Docker** y **Docker Compose** (v2)

---

## Requisitos Previos
Asegurate de tener instalado en tu equipo el siguiente software:
* Node.js (versión 24 LTS o superior)
* Git
* Docker Desktop (con el servicio activo)

---
## Ejecución Local (Sin Docker)

1. Clonar el repositorio e ingresar a la carpeta del proyecto.
2. Instalar dependencias (si aplica) o iniciar directamente los scripts definidos en el `package.json`:

**Modo desarrollo:**
    npm run dev

**Ejecutar pruebas automaticas**
    npm test

---
## Stages

**Stage de desarrollo**
Construye y levanta el entorno de desarrollo montando los volúmenes locales
* Ejecucion: docker compose --profile dev up --build
* Acceso : http://localhost:3000
* Para detenerlo: docker compose --profile dev down

**Stage de pruebas (test)**
Ejecuta las pruebas automáticas dentro de un contenedor aislado
* Ejecucion: docker compose --profile test up --build --abort-on-container-exit --exit-code-from app-test
* Para detenerlo: docker compose --profile test down

**Stage de produccion local**
Simula el empaquetado de producción de forma local
* Ejecucion: docker compose --profile prod up --build -d
* Acceso : http://localhost:8080 (expuesto desde el puerto interno 3000)
* Ver estado: docker compose --profile prod ps
* Para detenerlo: docker compose --profile prod down

## integrantes del grupo
    Tiago Escalante
    Lucas Alvarez 