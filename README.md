# Aplicación Full-Stack de Gestión de Usuarios con Spring Boot, React y Keycloak

![Java](https://img.shields.io/badge/Java-17-blue)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2.5-brightgreen)
![React](https://img.shields.io/badge/React-18-blueviolet)
![Vite](https://img.shields.io/badge/Vite-7.0-yellow)
![Keycloak](https://img.shields.io/badge/Keycloak-24.0.4-orange)

Este repositorio contiene una aplicación web full-stack completa que demuestra una integración de seguridad robusta entre un backend de Spring Boot y un frontend de React, utilizando **Keycloak** como servidor central de identidad y autorización.

El proyecto está organizado en un monorepo con dos componentes principales:
* **`/backend`**: Una API RESTful segura construida con Spring Boot que gestiona las operaciones de usuarios en Keycloak.
* **`/frontend`**: Una aplicación de una sola página (SPA) construida con React y Vite que proporciona una interfaz de usuario para interactuar con la API.

---

## ✨ Arquitectura y Flujo

1.  El usuario visita la aplicación de **React**.
2.  El frontend redirige al usuario a la página de login de **Keycloak** para autenticarse.
3.  Tras un login exitoso, Keycloak devuelve un **token JWT** al frontend.
4.  El frontend almacena este token y lo adjunta en la cabecera de autorización de cada petición a la API de **Spring Boot**.
5.  El backend de Spring Boot valida el token JWT contra Keycloak y verifica los roles del usuario para autorizar la operación.
6.  La API interactúa con el **Admin Client de Keycloak** para realizar operaciones CRUD sobre los usuarios.

---

## 🛠️ Tecnologías Utilizadas

-   **Backend (`/backend`)**
    -   Java 17
    -   Spring Boot 3.2.5
    -   Spring Security 6 (OAuth 2.0 Resource Server)
    -   Keycloak Admin Client 24.0.4
    -   Maven
-   **Frontend (`/frontend`)**
    -   React 18
    -   Vite
    -   Keycloak JS Adapter
    -   Axios
    -   CSS Modules

---

## 🚀 Cómo Ponerlo en Marcha

### 1. Prerrequisitos

-   Java 17 o superior
-   Node.js 18 o superior (con npm)
-   Docker (recomendado para Keycloak)
-   Maven

### 2. Configuración de Keycloak

(Asegúrate de que tu instancia de Keycloak esté corriendo y configurada como lo hicimos anteriormente, con los dos clientes: `spring-client-api-rest` y `frontend-app`, y los roles correspondientes).

### 3. Ejecutar el Backend

1.  Abre una terminal y navega a la carpeta del backend:
    ```bash
    cd backend
    ```
2.  Asegúrate de que tu archivo `src/main/resources/application.properties` tenga el `client-secret` correcto.
3.  Ejecuta la aplicación:
    ```bash
    mvn spring-boot:run
    ```
    El backend estará disponible en `http://localhost:8080`.

### 4. Ejecutar el Frontend

1.  Abre una **segunda terminal** y navega a la carpeta del frontend:
    ```bash
    cd frontend
    ```
2.  Instala las dependencias (solo la primera vez):
    ```bash
    npm install
    ```
3.  Inicia el servidor de desarrollo:
    ```bash
    npm run dev
    ```
    El frontend estará disponible en `http://localhost:5173` (o el puerto que indique la terminal).

### 5. ¡Listo!

Abre `http://localhost:5173` en tu navegador para usar la aplicación.

---

