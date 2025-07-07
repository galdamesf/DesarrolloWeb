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

---

# ✅ ACTIVIDAD 3 – Explorando las herramientas de desarrollo
🎯 Objetivo: Familiarizarse con las DevTools del navegador.
---
## **⌨️ Cómo Abrir DevTools**
Por Sistema Operativo:
Sistema OperativoMétodo 1Método 2Método 3🪟 WindowsF12Ctrl + Shift + IClick derecho → Inspeccionar🐧 LinuxF12Ctrl + Shift + IClick derecho → Inspeccionar🍎 MacF12Cmd + Option + IClick derecho → Inspeccionar
Métodos Alternativos:

Menú del navegador: Configuración → Más herramientas → DevTools
Inspeccionar elemento: Click derecho en cualquier elemento → "Inspeccionar"

---

## **🔍 Explorando las Pestañas Principales**
📋 1. Elements (Elementos)
La pestaña Elements te permite inspeccionar y modificar el HTML y CSS de la página en tiempo real.
Funcionalidades principales:

Inspeccionar HTML: Ver la estructura completa del DOM
Editar elementos: Modificar texto, atributos y etiquetas
Estilos CSS: Ver y modificar estilos aplicados
Computado: Ver los estilos finales calculados
Responsive: Simular diferentes tamaños de pantalla

Qué puedes hacer:

Cambiar texto directamente en la página
Modificar colores y estilos
Agregar o eliminar elementos
Ver qué CSS se está aplicando

---

## **🖥️ 2. Console (Consola)**
La Console es donde se muestran mensajes, errores y warnings del JavaScript.
Funcionalidades principales:

Errores de JavaScript: Muestra errores y stack traces
Warnings: Advertencias sobre código deprecated
Logs: Mensajes de console.log() del desarrollador
Ejecutar código: Puedes escribir JavaScript directamente

Tipos de mensajes:

🔴 Error: Errores críticos que rompen funcionalidad
🟡 Warning: Advertencias sobre mejores prácticas
🔵 Info: Información general del sistema
⚪ Log: Mensajes de debug del desarrollador

---

## **🌐 3. Network (Red)**
La pestaña Network muestra todas las solicitudes HTTP que hace la página.
Funcionalidades principales:

Solicitudes HTTP: GET, POST, PUT, DELETE
Recursos: Imágenes, CSS, JavaScript, fuentes
Tiempo de carga: Cuánto tarda cada recurso
Tamaño: Bytes transferidos y sin comprimir
Códigos de estado: 200, 404, 500, etc.

Información que muestra:

Name: Nombre del archivo o endpoint
Status: Código de respuesta HTTP
Type: Tipo de contenido (document, stylesheet, script)
Size: Tamaño del archivo
Time: Tiempo de descarga

---

## **💾 4. Storage (Almacenamiento)**
La pestaña Storage (o Application en algunos navegadores) gestiona el almacenamiento local.
Tipos de almacenamiento:

Local Storage: Datos persistentes por dominio
Session Storage: Datos temporales de la sesión
Cookies: Pequeños archivos de texto
IndexedDB: Base de datos local del navegador
Cache: Archivos almacenados en caché

---

## **🔬 Ejercicio Práctico: Inspeccionando Google.com**
Paso 1: Preparar el Entorno

Abre tu navegador
Ve a google.com
Abre DevTools con F12 o Ctrl/Cmd + Shift + I
Mantén DevTools abierto mientras navegas

Paso 2: Capturar una Solicitud HTTP
En la pestaña Network:

Ve a la pestaña Network
Actualiza la página (F5 o Ctrl/Cmd + R)
Observa cómo se cargan los recursos

Ejemplo de solicitud HTTP típica:
GET https://www.google.com/
Status: 200 OK
Method: GET
Response Headers:
  - Content-Type: text/html; charset=UTF-8
  - Set-Cookie: 1P_JAR=2025-01-15-10; expires=Thu, 14-Feb-2025 10:00:00 GMT
  - Cache-Control: private, max-age=0
Request Headers:
  - User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
  - Accept: text/html,application/xhtml+xml
Paso 3: Inspeccionar HTML de un Elemento
En la pestaña Elements:

Ve a la pestaña Elements
Busca el logo de Google
Haz click derecho en el logo → "Inspeccionar"

Ejemplo de HTML típico:
html<img class="lnXdpd" 
     alt="Google" 
     height="92" 
     src="/images/branding/googlelogo/2x/googlelogo_color_272x92dp.png" 
     width="272" 
     data-atf="1" 
     data-frt="0">
     
Paso 4: Buscar Errores en Consola
En la pestaña Console:

Ve a la pestaña Console
Busca mensajes rojos (errores) o amarillos (warnings)
Google generalmente es muy limpio, pero puedes encontrar warnings

Posibles mensajes que podrías ver:
javascript// Warning típico
⚠️ [Deprecation] Synchronous XMLHttpRequest is deprecated

// Error típico (si hubiera)
❌ Uncaught TypeError: Cannot read property 'value' of null

// Log informativo
ℹ️ Google Analytics loaded successfully

## **📸 Capturas Recomendadas**
1. Solicitud HTTP Principal

Captura la request principal de google.com
Muestra el status 200, headers y timing

2. Estructura HTML

Inspecciona el elemento del logo de Google
Muestra los atributos src, alt, width, height

3. Recursos de Red

Captura la lista completa de recursos cargados
Muestra imágenes, CSS, JavaScript

4. Almacenamiento Local

Ve a Storage → Cookies
Muestra las cookies que Google establece

---

## **🛠️ Consejos Prácticos**
Para Desarrolladores:

Usa el selector: Click en el icono de cursor para inspeccionar cualquier elemento
Edita en vivo: Doble-click en cualquier texto para editarlo
Copia elementos: Click derecho → Copy → Copy element
Simula dispositivos: Click en el ícono de móvil para responsive design

Para Depuración:

Breakpoints: Pausa la ejecución de JavaScript
Network throttling: Simula conexiones lentas
Console.log(): Añade mensajes de debug en tu código
Preserve log: Mantén los logs al navegar entre páginas

---

## **🎯 Actividades Adicionales**

Experimenta con CSS:

Cambia el color del logo de Google
Modifica el tamaño de la barra de búsqueda


Analiza Performance:

Ve a la pestaña Performance
Graba la carga de la página


Explora APIs:

En Console, ejecuta: navigator.geolocation.getCurrentPosition(console.log)
Prueba: document.querySelector('input[name="q"]').value = 'DevTools'


Inspecciona Cookies:

Ve a Storage → Cookies
Observa qué información guarda Google

---

## **🔒 Nota de Seguridad**
Las DevTools son herramientas poderosas que te permiten:

✅ Inspeccionar cualquier sitio web
✅ Modificar la apariencia localmente
✅ Analizar el código frontend
❌ NO modificar el servidor real
❌ NO acceder a datos de otros usuarios

Los cambios que hagas solo son visibles para ti y se pierden al recargar la página.
