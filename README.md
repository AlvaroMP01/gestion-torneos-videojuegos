# 🏆 Plataforma de Gestión de Torneos de Videojuegos (Valorant)

## 1. Descripción del Proyecto
Este proyecto consiste en el desarrollo de una aplicación web para la gestión integral de torneos de videojuegos online (centrado en Valorant). El objetivo principal es solucionar el desorden actual en la organización de competiciones amateurs, las cuales suelen gestionarse de forma improvisada mediante redes sociales.

La plataforma centraliza la información, facilitando la inscripción de equipos, la gestión de roles (capitanes, administradores) y el seguimiento de resultados y estadísticas en tiempo real mediante una arquitectura moderna y escalable.

## 2. Arquitectura y Tecnologías 🛠️
El proyecto sigue una arquitectura **Cliente-Servidor (RESTful)** contenerizada, separando claramente la lógica de negocio de la interfaz de usuario.

### Stack Tecnológico

* **Frontend (Cliente):**

    * **React.js (Vite):** Para una interfaz de usuario rápida y reactiva.

    * **JavaScript (ES6+):** Lenguaje principal del cliente.

    * **Tailwind CSS:** Para un diseño moderno, responsive y ágil.

* **Backend (API):**

    * **Python (Flask):** Framework ligero para la creación de la API REST.

    * **SQLAlchemy:** ORM para la gestión de modelos de datos y consultas SQL seguras.

    * **Flask-JWT-Extended:** Para la autenticación segura mediante Tokens.

* **Base de Datos:**


    * **MySQL 8.0:** Base de datos relacional para la persistencia de usuarios, torneos y estadísticas.

* **DevOps & Infraestructura:**

    * **Docker & Docker Compose:** Para la orquestación de contenedores y despliegue unificado.

## 3. Estructura del Proyecto

El código está organizado siguiendo las buenas prácticas de separación de responsabilidades:

```text
/gestion-torneos-videojuegos
├── docker-compose.yml       # Orquestación de servicios (BD, Backend, Frontend)
├── .env                     # Variables de entorno (Credenciales BD, Secret Keys)
├── README.md                # Documentación del proyecto
│
├── backend/                 # API REST (Python Flask)
│   ├── Dockerfile
│   ├── requirements.txt     # Dependencias del servidor
│   ├── app.py               # Punto de entrada
│   └── src/
│       ├── models/          # Modelos de BD (User, Team, Tournament)
│       └── routes/          # Endpoints de la API
│
└── frontend/                # SPA (React JS)
    ├── Dockerfile
    ├── package.json         # Dependencias del cliente
    ├── vite.config.js       # Configuración de compilación
    └── src/
        ├── components/      # Componentes reutilizables
        └── pages/           # Vistas principales
```

## 4. Modelo de Datos (ERD) 💾

* **El sistema gestiona las siguientes entidades principales:**

  * **Users:** Usuarios de la plataforma con roles (Admin, Capitán, Jugador).

  * **Teams:** Equipos creados por capitanes, con escudo y tag.

  * **Tournaments:** Competiciones con fechas, premios y estado.

  * **Matches:** Enfrentamientos individuales dentro de un torneo.

  * **Statistics:** Rendimiento individual (KDA) de los jugadores por partido.

## 5. Funcionalidades (MVP)

* **Para cumplir con los objetivos del proyecto, la aplicación cuenta con:**

  * **Gestión de Usuarios y Roles:** Registro, Login (JWT) y perfiles diferenciados.

  * **Gestión de Equipos:** Creación de equipos, invitación de miembros y gestión de capitanes.

  * **Sistema de Torneos:** Inscripción de equipos a torneos abiertos y generación de brackets.

  * **Panel de Administración:** Interfaz para gestionar resultados de partidos y crear competiciones.

  * **Visualización Pública:** Tablas de clasificación y detalles de los torneos.

## 6. Instalación y Despliegue

Este proyecto está diseñado para levantarse con un solo comando gracias a Docker.

Requisitos previos

  * Docker Desktop instalado.

  * Git.

### Pasos

**1. Clonar el repositorio:**

```Bash
  git clone [https://github.com/AlvaroMP01/gestion-torneos-videojuegos.git](https://github.com/AlvaroMP01/gestion-torneos-videojuegos.git)
  cd gestion-torneos-videojuegos
```

**2. Configurar variables de entorno:**

Crea un archivo .env en la raíz basado en el ejemplo proporcionado (o usa los valores por defecto del docker-compose.yml).

**3. Levantar la aplicación:**

```Bash
  docker-compose up --build
```

**4. Acceso:**

* Frontend: <http://localhost:5173>

* Backend API: <http://localhost:5000>

* Base de Datos (Puerto expuesto): ```3306```

## 7. Autor

Proyecto realizado por Álvaro Morcillo Pérez como Trabajo de Fin de Grado (TFG).
Repositorio: <https://github.com/AlvaroMP01/gestion-torneos-videojuegos>