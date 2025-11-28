# Rushav Backend - API RESTful E-commerce

Este repositorio contiene la lógica del lado del servidor para la plataforma de comercio electrónico "Rushav". El sistema está construido utilizando Java con el framework Spring Boot y sigue una arquitectura de API RESTful.

## Descripción del Proyecto

El backend gestiona la autenticación de usuarios, la administración de inventario (productos y categorías), el procesamiento de pedidos y la persistencia de datos. Implementa seguridad avanzada mediante JSON Web Tokens (JWT) y maneja excepciones globales para asegurar la integridad referencial de la base de datos.

## Tecnologías Utilizadas

* **Lenguaje:** Java (JDK 17)
* **Framework Principal:** Spring Boot 3.3.x
* **Seguridad:** Spring Security con configuración Stateless.
* **Autenticación:** JWT (JSON Web Token) con librería JJWT.
* **Base de Datos:** MySQL 8.0.
* **ORM:** Spring Data JPA / Hibernate.
* **Documentación:** Springdoc OpenAPI (Swagger UI).
* **Gestión de Dependencias:** Maven.

## Requisitos Previos

Antes de ejecutar la aplicación, asegúrese de tener instalado:

1.  Java Development Kit (JDK) versión 17 o superior.
2.  MySQL Server en ejecución (puerto 3306 por defecto).
3.  Maven (opcional, el proyecto incluye el wrapper `mvnw`).

## Instrucciones de Instalación y Configuración de Base de Datos

1.  **Clonar el repositorio:**
    Descargue el código fuente desde el repositorio de GitHub.

2.  **Configuración de la Base de Datos:**
    El sistema requiere una base de datos MySQL creada previamente. Abra su cliente de base de datos (MySQL Workbench, DBeaver, o línea de comandos) y ejecute:
    ```sql
    CREATE DATABASE rushav_db;
    ```

## Instrucciones de Ejecución

Para iniciar el servidor, abra una terminal en la raíz del proyecto y ejecute el siguiente comando según su sistema operativo:

**En Windows:**
```bash
./mvnw.cmd spring-boot:run
En macOS / Linux:

Bash

./mvnw spring-boot:run
El servidor iniciará en el puerto 8080. La primera ejecución puede tardar unos minutos mientras se descargan las dependencias y se inicializa la estructura de la base de datos.

Nota: El sistema está configurado con spring.jpa.hibernate.ddl-auto=create-drop y spring.sql.init.mode=always. Esto significa que al iniciar la aplicación, las tablas se crearán automáticamente y se poblarán con datos de prueba (semilla) definidos en data.sql.

Documentación de la API
El proyecto incluye documentación interactiva generada automáticamente con Swagger. Una vez que la aplicación esté en ejecución, puede acceder a ella en la siguiente URL:

URL: http://localhost:8080/swagger-ui.html

Desde esta interfaz es posible visualizar todos los endpoints disponibles, los modelos de datos (DTOs) y probar las peticiones HTTP directamente.

Credenciales de Prueba
El sistema se inicializa con un usuario administrador por defecto para facilitar las pruebas de los endpoints protegidos y el panel de administración.

Rol: Super Admin

Correo Electrónico: admin@rushav.cl

Contraseña: admin123

Para acceder a los endpoints protegidos en Swagger, debe utilizar el endpoint /api/auth/login con estas credenciales, copiar el token JWT resultante y utilizar el botón "Authorize" en la parte superior de la interfaz Swagger.
