# Desarrollo Web
# ✅ ACTIVIDAD 1 – ¿Esto es una web o una app web?

🎯 **Objetivo**: Comprender la diferencia entre un sitio web estático y una aplicación web interactiva.

---

### **🔍 3 Ejemplos de Sitios Web Informativos**

- **Wikipedia** – Enciclopedia en línea que presenta información estática organizada en artículos.  
- **BBC News** – Portal de noticias que muestra contenido informativo actualizado.  
- **Blog personal de un desarrollador** – Sitio que publica artículos y tutoriales de programación.

---

### **🚀 3 Ejemplos de Aplicaciones Web**

- **Gmail** – Cliente de correo electrónico con funciones de composición, envío y gestión.  
- **Figma** – Herramienta de diseño colaborativo en tiempo real.  
- **Google Docs** – Procesador de texto colaborativo con edición en tiempo real.

---

### **🤔 Justificación de la Clasificación**

**Sitios Web Informativos:**

- Su propósito principal es mostrar información de manera estática.  
- La interacción del usuario se limita a navegar y consumir contenido.  
- No requieren autenticación compleja ni mantienen estados de usuario.  
- El contenido se presenta de forma unidireccional (del sitio al usuario).

**Aplicaciones Web:**

- Permiten a los usuarios crear, modificar y gestionar datos.  
- Requieren interacciones complejas y mantienen estados de sesión.  
- Ofrecen funcionalidades específicas que van más allá de mostrar información.  
- Proporcionan experiencias personalizadas según el usuario.

---

### **💡 ¿Qué hace que una aplicación web sea interactiva?**

Una aplicación web es interactiva porque:

- Responde dinámicamente a las acciones del usuario.  
- Procesa y almacena datos ingresados por el usuario.  
- Mantiene estados y recuerda información entre sesiones.  
- Actualiza contenido sin necesidad de recargar la página completa.  
- Permite colaboración entre múltiples usuarios en tiempo real.

---

### **🛠️ Tecnologías que podrían estar detrás**

**Frontend (Cliente):**

- JavaScript para la lógica interactiva.  
- Frameworks como React, Vue o Angular para interfaces dinámicas.  
- CSS avanzado para animaciones y transiciones.

**Backend (Servidor):**

- Bases de datos (MySQL, PostgreSQL, MongoDB) para almacenar datos.  
- APIs REST o GraphQL para comunicación cliente-servidor.  
- Lenguajes de servidor (Node.js, Python, Java, PHP).

**Comunicación:**

- AJAX / Fetch API para actualizaciones asíncronas.  
- WebSockets para comunicación en tiempo real.  
- JSON como formato de intercambio de datos.

---

### **🎯 Conclusión**

La clave está en que **las aplicaciones web crean un diálogo bidireccional** entre el usuario y el sistema, mientras que **los sitios web informativos principalmente presentan contenido de manera unidireccional**.

---

# ✅ ACTIVIDAD 2 – Anatomía de una aplicación web moderna
## **🎯 Objetivo**: Comprender los componentes principales de una app web (frontend, backend, base de datos).

---

## **🔍 Conceptos Principales**
🖥️ Frontend (Cliente)
El frontend es la parte visible de la aplicación web con la que interactúa directamente el usuario. Es todo lo que ves y tocas en tu navegador.
Características:

Interfaz de usuario (botones, formularios, menús)
Experiencia de usuario (navegación, animaciones, diseño)
Lógica del cliente (validaciones, interacciones)
Presentación de datos (gráficos, tablas, contenido)

Tecnologías comunes:

HTML - Estructura del contenido
CSS - Estilos y diseño visual
JavaScript - Interactividad y lógica
Frameworks: React, Vue.js, Angular

---

## **⚙️ Backend (Servidor)**
El backend es la parte invisible que maneja la lógica de negocio, procesa datos y gestiona las comunicaciones. Es el "cerebro" de la aplicación.
Características:

Lógica de negocio (cálculos, reglas, algoritmos)
Procesamiento de datos (validaciones, transformaciones)
Autenticación y autorización (login, permisos)
APIs (puntos de comunicación con el frontend)

Tecnologías comunes:

Lenguajes: Node.js, Python, Java, PHP, C#
Frameworks: Express, Django, Spring, Laravel
Servidores: Apache, Nginx

---

## **🗄️ Base de Datos**
La base de datos es el sistema de almacenamiento donde se guardan, organizan y gestionan todos los datos de la aplicación de manera persistente.
Características:

Almacenamiento persistente (datos que no se pierden)
Organización estructurada (tablas, documentos, grafos)
Consultas eficientes (búsquedas, filtros, ordenamientos)
Integridad de datos (consistencia, validaciones)

Tipos y tecnologías:

SQL: MySQL, PostgreSQL, SQLite
NoSQL: MongoDB, Redis, Firebase
Cloud: AWS RDS, Google Cloud SQL

---

## **🔄 Diagrama de Comunicación**
mermaidgraph TD
    A[👤 Usuario] --> B[🖥️ Frontend<br/>HTML, CSS, JS]
    B --> C[🌐 HTTP/HTTPS<br/>Requests/Responses]
    C --> D[⚙️ Backend<br/>Servidor + API]
    D --> E[🗄️ Base de Datos<br/>MySQL, MongoDB]
    E --> D
    D --> C
    C --> B
    B --> A
    
    style A fill:#e1f5fe
    style B fill:#f3e5f5
    style D fill:#e8f5e8
    style E fill:#fff3e0

---
    
## **🚀 Flujo de Comunicación**
1. Usuario → Frontend

El usuario interactúa con la interfaz (clicks, formularios, navegación)
El frontend captura las acciones y las procesa localmente

2. Frontend → Backend

El frontend envía requests HTTP al servidor
Incluye datos del usuario (formularios, filtros, comandos)
Utiliza métodos como GET, POST, PUT, DELETE

3. Backend → Base de Datos

El servidor procesa la request y determina qué datos necesita
Realiza consultas SQL o queries NoSQL a la base de datos
Aplica lógica de negocio y validaciones

4. Base de Datos → Backend

La base de datos devuelve los resultados solicitados
Puede ser información, confirmaciones o errores

5. Backend → Frontend

El servidor procesa los datos y envía una response HTTP
Incluye los datos en formato JSON, XML o HTML
Puede incluir códigos de estado (200, 404, 500)

6. Frontend → Usuario

El frontend recibe la respuesta y actualiza la interfaz
Muestra los datos al usuario de forma visual
Puede mostrar mensajes de éxito o error

---

## **💡 Ejemplo Práctico: Sistema de Login**
mermaidsequenceDiagram
    participant U as 👤 Usuario
    participant F as 🖥️ Frontend
    participant B as ⚙️ Backend
    participant DB as 🗄️ Base de Datos
    
    U->>F: Ingresa email y password
    F->>F: Valida formato localmente
    F->>B: POST /login {email, password}
    B->>B: Valida credenciales
    B->>DB: SELECT user WHERE email=?
    DB->>B: Retorna datos del usuario
    B->>B: Verifica password encriptado
    B->>F: Response: {token, user_data}
    F->>F: Guarda token y actualiza UI
    F->>U: Muestra dashboard del usuario
    
---

## **🎯 Puntos Clave**

Separación de responsabilidades: Cada capa tiene una función específica
Comunicación asíncrona: Las requests no bloquean la interfaz
Escalabilidad: Cada componente puede mejorarse independientemente
Seguridad: El backend valida y protege los datos sensibles
Experiencia de usuario: El frontend mantiene la aplicación responsive

---

## **🛠️ Herramientas para Crear Diagramas**

Mermaid Live: https://mermaid.live (online, gratuito)
Draw.io: https://app.diagrams.net (diagramas visuales)
Lucidchart: Para diagramas profesionales
Figma: Para wireframes y diseños de UI
