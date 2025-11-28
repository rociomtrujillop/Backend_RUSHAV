# Rushav Backend - API RESTful E-commerce

Este repositorio contiene la lógica del servidor para la plataforma de comercio electrónico "Rushav". El sistema está construido utilizando Java con el framework Spring Boot y sigue una arquitectura de API RESTful.

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

## Instrucciones de Instalación y Configuración

1.  **Clonar el repositorio:**
    Descargue el código fuente en su equipo local.

2.  **Creación de Base de Datos:**
    El sistema requiere un esquema de base de datos vacío. Abra su cliente MySQL (Workbench, DBeaver o consola) y ejecute:
    ```sql
    CREATE DATABASE rushav_db;
    ```

3.  **Configuración de Credenciales:**
    El archivo de configuración se encuentra en `src/main/resources/application.properties`. Por defecto, está configurado para el usuario `root` sin contraseña. Si su instalación local de MySQL tiene contraseña, modifique las líneas:
    ```properties
    spring.datasource.username=root
    spring.datasource.password=SU_CONTRASEÑA_AQUI
    ```

## Instrucciones de Ejecución

Para iniciar el servidor, abra una terminal en la raíz del proyecto y ejecute el siguiente comando:

**En Windows:**
```bash
./mvnw.cmd spring-boot:run
En macOS / Linux:

Bash

./mvnw spring-boot:run
El servidor iniciará en el puerto 8080.

Nota sobre Persistencia: El sistema está configurado con spring.jpa.hibernate.ddl-auto=create-drop y spring.sql.init.mode=always. Esto significa que al iniciar la aplicación, las tablas se crearán automáticamente y se poblarán con los datos de prueba definidos en data.sql.

Documentación de la API (Swagger)
El proyecto incluye documentación interactiva. Una vez que la aplicación esté en ejecución, acceda a:

URL: http://localhost:8080/swagger-ui.html

Desde esta interfaz es posible visualizar todos los endpoints disponibles, los modelos de datos (DTOs) y probar las peticiones HTTP directamente.

Credenciales de Prueba
El sistema se inicializa con un usuario administrador por defecto para acceder a las rutas protegidas y al panel de administración:

Rol: Super Admin

Correo Electrónico: admin@rushav.cl

Contraseña: admin123

Instrucciones de Autenticación en Swagger:

Utilice el endpoint /api/auth/login con las credenciales anteriores.

Copie el token JWT de la respuesta.

Haga clic en el botón "Authorize" en la parte superior y pegue el token con el formato: Bearer SU_TOKEN.

Scripts SQL (Entregable)
Aunque la aplicación genera el esquema automáticamente, los scripts SQL físicos solicitados en la evaluación (creacion_tablas.sql y datos_prueba.sql) se encuentran adjuntos en la carpeta principal de la entrega comprimida (.zip) para su revisión manual si fuera necesario.

## Nota sobre Script de Datos (Seed Data)

Para efectos de evaluación del punto "Script con datos de prueba", el archivo SQL que contiene la población inicial de la base de datos (Usuarios y Productos) se encuentra ubicado dentro de la estructura del proyecto en:

`src/main/resources/data.sql`

Este script se ejecuta automáticamente al iniciar la aplicación para garantizar que el entorno de pruebas esté listo.
