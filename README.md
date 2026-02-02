# 📦 Sistema de Gestión de Paquetería - Full Stack - Proyecto Academico UADE

![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.109-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Render](https://img.shields.io/badge/Deploy-Render-46E3B7?style=for-the-badge&logo=render&logoColor=white)

Plataforma integral para la logística y seguimiento de envíos. Este proyecto evoluciona una lógica de negocio algorítmica compleja hacia una **Arquitectura Web Escalable**, priorizando la integridad de datos y la seguridad en el Backend.

🔗 **[Ver Demo en Vivo](https://sistemaseguimientoenviosapi.onrender.com)** 📄 **[Documentación API (Swagger)](https://sistemaseguimientoenviosapi.onrender.com/docs)**

---

## 🧠 Enfoque Técnico: "Zero Trust Architecture"

A diferencia de aplicaciones web estándar que confían en el frontend, este sistema implementa una capa de **Lógica de Negocio Estricta** en Python que blinda la base de datos.

### 🛡️ Backend (El Núcleo)
* **Validación Robusta:** Implementación de algoritmos de normalización de texto y verificación contra listas oficiales (ej. las 24 jurisdicciones de Argentina), rechazando cualquier dato que no cumpla el estándar, incluso si bypassesa el frontend.
* **Máquina de Estados Segura:** Lógica de control que impide transiciones ilegales (ej. prohibición sistémica de cancelar un pedido que ya figura como "Entregado").
* **PostgreSQL & Pooling:** Persistencia de datos profesional utilizando `psycopg2` con pool de conexiones para manejo eficiente de concurrencia.

### 🎨 Frontend (La Interfaz)
* **Diseño Glassmorphism:** Interfaz moderna y limpia construida con HTML5, Bootstrap 5 y CSS3.
* **Feedback en Tiempo Real:** Comunicación asíncrona con la API para informar al usuario sobre las validaciones del servidor mediante alertas nativas.

---

## 🛠️ Stack Tecnológico

| Componente | Tecnología | Uso en el Proyecto |
| :--- | :--- | :--- |
| **Lenguaje** | Python 3.11 | Lógica de negocio y algoritmos de validación. |
| **Framework API** | FastAPI | Creación de endpoints RESTful de alto rendimiento. |
| **Base de Datos** | PostgreSQL (Neon) | Almacenamiento relacional persistente. |
| **Validación** | Pydantic + Custom Logic | Sanitización de inputs y reglas de negocio. |
| **Frontend** | JS Vanilla + Bootstrap | Consumo de API y experiencia de usuario (SPA). |
| **Infraestructura** | Render + Docker Env | Despliegue continuo (CI/CD) en la nube. |

---

## 📂 Estructura del Proyecto

El código sigue una arquitectura limpia que separa la definición de la API de la lógica pura:

```text
sistema-envios-api/
├── src/
│   ├── main_postgres.py        # 🎮 Controlador: Endpoints y Modelos Pydantic
│   ├── logica_envios_postgres.py # 🧠 Lógica Pura: Validaciones, Algoritmos y DB
│   ├── index.html              # 🖥️ Vista: Interfaz de Usuario
│   └── requirements_postgres.txt # 📦 Dependencias
└── render.yaml                 # ☁️ IaC: Configuración de Infraestructura
