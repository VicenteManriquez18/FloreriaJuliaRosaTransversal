# Proyecto Florería Full Stack

Este documento contiene las instrucciones para la instalación, ejecución y prueba de los componentes del frontend y backend del proyecto.

## 1. Backend (Spring Boot)

### 1.1. Requisitos Previos

*   Java Development Kit (JDK) 21 o superior.
*   Apache Maven.
*   Un servidor de base de datos MySQL en ejecución.

### 1.2. Instalación

1.  **Crear la Base de Datos:**
    Asegúrate de que tu servidor MySQL esté en funcionamiento. Crea una nueva base de datos llamada `base`.
    ```sql
    CREATE DATABASE base;
    ```

2.  **Configurar la Conexión:**
    El archivo `projectbackend/src/main/resources/application.properties` está configurado para conectarse a `jdbc:mysql://localhost:3306/base` con el usuario `root` y sin contraseña. Ajusta estos valores si tu configuración de MySQL es diferente.

3.  **Instalar Dependencias:**
    Maven gestionará las dependencias automáticamente al ejecutar el proyecto. No se requiere un paso de instalación manual.

### 1.3. Ejecución

1.  Navega a la carpeta raíz del backend:
    ```sh
    cd projectbackend
    ```

2.  Ejecuta la aplicación usando el plugin de Maven para Spring Boot:
    ```sh
    mvn spring-boot:run
    ```

    El servidor se iniciará en el puerto `8081`.

### 1.4. Documentación de la API (Swagger)

Una vez que el backend esté en ejecución, puedes acceder a la documentación interactiva de la API de Swagger en tu navegador:

[http://localhost:8081/swagger-ui.html](http://localhost:8081/swagger-ui.html)

### 1.5. Credenciales de Prueba

La base de datos se llenará con los siguientes datos de prueba (`import.sql`):

*   **Rol Administrador:**
    *   **Usuario:** `admin@gmail.com`
    *   **Contraseña:** `admin123`

*   **Rol Usuario:**
    *   **Usuario:** `maria@gmail.com`
    *   **Contraseña:** `user123`
    *   (Y otros usuarios de prueba como `juan@gmail.com`, `carla@gmail.com`, etc., todos con la contraseña `user123`)

## 2. Frontend (React)

### 2.1. Requisitos Previos

*   Node.js
*   npm (normalmente incluido con Node.js)

### 2.2. Instalación

1.  Navega a la carpeta raíz del frontend:
    ```sh
    cd floreriaReact/floreriaReact
    ```

2.  Instala las dependencias del proyecto:
    ```sh
    npm install
    ```

### 2.3. Ejecución

1.  Dentro de la carpeta `floreriaReact/floreriaReact`, ejecuta el siguiente comando para iniciar el servidor de desarrollo:
    ```sh
    npm run dev
    ```

2.  Abre tu navegador y ve a la dirección que se indica en la terminal (generalmente `http://localhost:5173`).

---

## 3. Base de Datos

*   **Script de Creación de Tablas:** No se requiere un script manual. Al ejecutar el backend, JPA/Hibernate creará o actualizará automáticamente las tablas en la base de datos `base` según la configuración `spring.jpa.hibernate.ddl-auto=update`.
*   **Script de Datos de Prueba:** Los datos iniciales para categorías, productos y usuarios se insertan desde el archivo `projectbackend/src/main/resources/import.sql`.

