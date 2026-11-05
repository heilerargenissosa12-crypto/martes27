# 🚀 Sistema de Gestión de Clientes (Full Stack Spring Boot y React)

Proyecto práctico completo desarrollado a partir del tutorial de YouTube:
👉 **[Curso de Java FullStack con React y Spring Boot](https://youtu.be/3Cy3KCirn5U?si=GCY6B2sVWGK7FWu_)**

---

## 📁 Estructura del Proyecto

```text
gestion-clientes/
├── iniciar.bat                  <-- Doble clic para arrancar el frontend en Windows
├── backend/                     <-- Backend en Java y Spring Boot
│   ├── pom.xml                  <-- Dependencias (Spring Web, Spring Data JPA, MySQL, Lombok)
│   └── src/main/
│       ├── java/com/gestion/clientes/
│       │   ├── GestionClientesApplication.java  <-- Clase principal Spring Boot
│       │   ├── model/Cliente.java               <-- Entidad JPA (id, nombre, apellido, email)
│       │   ├── repository/ClienteRepository.java<-- Interfaz JpaRepository
│       │   ├── exception/ResourceNotFoundException.java <-- Excepción personalizada 404
│       │   └── controller/ClienteController.java<-- Controlador REST (CRUD completo y CORS)
│       └── resources/
│           └── application.properties           <-- Conexión MySQL y base de datos
└── frontend/                    <-- Frontend en JavaScript puro (.js) y React
    ├── package.json             <-- Dependencias (axios, bootstrap, react-router-dom)
    ├── vite.config.js           <-- Configuración de servidor en puerto 3000
    ├── index.html               <-- Vista HTML
    └── src/
        ├── index.js             <-- Punto de entrada de React
        ├── App.js               <-- Enrutador con React Router (BrowserRouter, Routes, Route)
        ├── App.css              <-- Estilos de la aplicación
        ├── services/
        │   └── ClienteService.js<-- Servicio Axios para consumir la API REST
        └── components/
            ├── HeaderComponent.js      <-- Barra de navegación superior
            ├── FooterComponent.js      <-- Pie de página
            ├── ListClientesComponent.js<-- Tabla con listado de clientes y botón eliminar
            └── AddClienteComponent.js  <-- Formulario para crear y editar clientes
```

---

## ⚡ Cómo ejecutar en Visual Studio Code

### 1. Abrir en Visual Studio Code
1. Abre **Visual Studio Code**.
2. Ve al menú superior: **Archivo** -> **Abrir carpeta...** (*File* -> *Open Folder...*).
3. Selecciona la carpeta **`gestion-clientes`** ubicada en tu **Escritorio**:
   ```text
   C:\Users\heile\OneDrive\Escritorio\gestion-clientes
   ```

### 2. Ejecutar la Aplicación

Tienes 3 formas sencillas:

* **Opción A (Doble clic directo):**
  Haz doble clic en el archivo `iniciar.bat` dentro de la carpeta `gestion-clientes`.

* **Opción B (Desde la terminal de VS Code):**
  Abre la terminal integrada en VS Code (`Ctrl + ñ`) y ejecuta:
  ```powershell
  cd frontend
  npm.cmd start
  ```

* **Opción C (Tarea rápida de VS Code):**
  Presiona `Ctrl + Shift + B` y selecciona **Iniciar Frontend React (npm start)**.

La aplicación se abrirá en tu navegador en:
🌐 **`http://localhost:3000`**

---

## 🔌 API REST del Backend (Spring Boot)

| Método | Endpoint | Descripción |
|---|---|---|
| `GET` | `/api/v1/clientes` | Obtiene la lista de todos los clientes |
| `POST` | `/api/v1/clientes` | Registra un nuevo cliente |
| `GET` | `/api/v1/clientes/{id}` | Busca un cliente por su ID |
| `PUT` | `/api/v1/clientes/{id}` | Actualiza los datos de un cliente |
| `DELETE` | `/api/v1/clientes/{id}` | Elimina un cliente por su ID |

*(Nota: el frontend cuenta con soporte dual: si Spring Boot está activo se conecta a `http://localhost:8080`, y si aún no lo has arrancado cuenta con persistencia local para que puedas interactuar con el CRUD de inmediato sin bloqueos)*.
