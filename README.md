# The Elder Cards BACKEND

> **API y servidor para la plataforma The Elder Cards. Proyecto FullStack que integra todo lo aprendido en Node.js, Express, MongoDB y más.**

---

## Índice

- [Descripción General](#descripción-general)
- [Características Principales](#características-principales)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
- [Instalación y Configuración](#instalación-y-configuración)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Arquitectura y Colecciones](#arquitectura-y-colecciones)
- [Endpoints y WebSocket](#endpoints-y-websocket)
- [Variables de Entorno](#variables-de-entorno)
- [Check de Requerimientos](#check-de-requerimientos)
- [Licencia y Reconocimientos](#licencia-y-reconocimientos)

---

## Descripción General

**The Elder Cards BACKEND** es la API y servidor que da soporte a la plataforma web, permitiendo la gestión de usuarios, cartas, colecciones, facciones, bestiario y mensajería en tiempo real. El proyecto está diseñado para ser el último reto del curso, integrando todo lo aprendido y resolviendo un problema real con una arquitectura profesional.

---

## Características Principales

- API RESTful para usuarios, cartas, facciones, colecciones, bestiario y mensajes
- WebSocket en tiempo real con Socket.IO para notificaciones y chat
- Autenticación JWT y roles de usuario
- Subida de imágenes con Cloudinary (opcional y puntuable)
- Base de datos MongoDB con modelos relacionales
- Semillas automáticas desde Excel/CSV usando Node.js (fs)
- Protección de rutas según rol y autenticación
- Despliegue sencillo en Render

---

## Tecnologías Utilizadas

- **Node.js**
- **Express**
- **MongoDB** (Mongoose)
- **Socket.IO**
- **Cloudinary** (opcional)
- **JWT**
- **dotenv**
- **fs** (lectura/escritura de archivos)
- **Otras librerías opcionales y recomendadas**

---

## Instalación y Configuración

1. **Instala dependencias:**
   ```bash
   npm install
   ```
2. **Configura variables de entorno:**
   - Copia `.env.example` a `.env` y edita tus credenciales
3. **Ejecuta en desarrollo:**
   ```bash
   npm run dev
   ```
4. **Ejecuta en producción:**
   ```bash
   npm start
   ```

---

## Estructura del Proyecto

```
The-Elder-Cards-BACKEND/
├── src/
│   ├── api/
│   │   ├── controllers/      # Lógica de negocio y endpoints
│   │   ├── models/           # Modelos de Mongoose
│   │   ├── routes/           # Rutas de la API
│   ├── config/               # Configuración de BBDD y sockets
│   ├── middlewares/          # Middlewares de autenticación, subida, etc.
│   ├── utils/                # Utilidades (generador de cartas, helpers)
├── fonts/                    # Fuentes utilizadas
├── output/                   # Archivos generados
├── render.yaml               # Configuración para Render
├── package.json              # Dependencias y scripts
├── README.md                 # Documentación
```

---

## Arquitectura y Colecciones

- **Usuarios**: Roles, autenticación, perfil, permisos
- **Cartas**: Datos, imágenes, estadísticas, relación con facciones y usuarios
- **Colecciones**: Relación entre cartas y usuarios, públicas/privadas
- **Facciones**: Historia, territorio, color, imagen
- **Bestiario**: Criaturas y artefactos, con relación a cartas y hechizos
- **Mensajes**: Chat privado entre usuarios

**Semillas:**

- Generadas a partir de un Excel/CSV con mínimo 100 datos y 2/3 colecciones relacionadas
- Uso de Node.js (`fs`) para leer y poblar la base de datos

---

## Endpoints y WebSocket

- `GET /` - Info de la API
- `GET /api/health` - Health check
- `POST /api/v1/users/register` - Registro de usuario
- `POST /api/v1/users/login` - Login
- `GET /api/v1/cards` - Listar cartas
- `GET /api/v1/factions` - Listar facciones
- `WebSocket` - Notificaciones y chat en tiempo real

**Socket.IO:**

- WebSocket (preferido) y polling (fallback)
- Autenticación por token JWT

---

## Variables de Entorno

Ver `.env.example` para la lista completa de variables requeridas:

- `NODE_ENV`, `DB_URL`, `SECRET_KEY`, `CLIENT_URL`, `CLOUDINARY_CLOUD_NAME`, `CLOUDINARY_API_KEY`, `CLOUDINARY_API_SECRET`, etc.

---

## Check de Requerimientos

Este proyecto cumple con todos los requisitos del último proyecto FullStack del curso:

- [x] Proyecto con sentido, resuelve un problema y está enfocado a un público concreto.
- [x] Temática libre, con lógica y buen UX/UI en el frontend.
- [x] Utiliza **Node.js** en el backend y **React** en el frontend.
- [x] Uso opcional y recomendado de librerías vistas en el curso y otras nuevas (puntuable).
- [x] Arquitectura clara y estructurada, fácil de entender para cualquier persona.
- [x] Base de datos inicial generada a partir de un Excel con mínimo 100 datos y 2/3 colecciones relacionadas entre sí.
- [x] Lectura/escritura de archivos con Node.js (`fs`) para extraer datos y crear semillas.
- [x] Modelos de colecciones creados previamente para la semilla.
- [x] Colección de usuarios en el backend, con roles y rutas protegidas según rol/login.
- [x] Uso opcional de Cloudinary para subida de imágenes (form-data).
- [x] Despliegue de **BACKEND** y **FRONTEND** accesible mediante enlaces públicos.
- [x] ReadMe detallado explicando el sentido detrás del proyecto y demostrando el cumplimiento de todos los requisitos.

**Ejemplo de Excel utilizado:** [Enlace de ejemplo de concesionario](https://docs.google.com/spreadsheets/d/1eWsdvriKPBOs1JXID0gz8jhIuXKaK5XcUQdjbqcpVhI/edit?usp=sharing)

---

## Licencia y Reconocimientos

- **The Elder Cards** es un proyecto sin ánimo de lucro, creado por fans y para fans.
- No está afiliado ni respaldado por Bethesda Softworks, ZeniMax Media ni ninguna empresa titular de marcas registradas mencionadas.
- Todos los nombres, logotipos, imágenes y contenido relacionado son propiedad de sus respectivos dueños.
- El uso de elementos de terceros se realiza bajo el principio de _fair use_ y homenaje creativo, sin fines comerciales.
- Si eres titular de derechos y tienes alguna preocupación, contáctanos para resolver cualquier problema de inmediato.

---

**Última actualización:** Octubre 2025
