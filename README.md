# __LAB 5.1: Aplicación__

## Capítulo 1: Creación proyecto Spring Boot

## Tutorial: Creación de un Proyecto Spring Boot con un Servicio "Hello World"

### 1. Introducción a Spring Boot
Spring Boot es un marco de trabajo de código abierto que simplifica el desarrollo de aplicaciones Spring independientes y de calidad de producción. Está construido sobre el Spring Framework y proporciona una variedad de herramientas, bibliotecas y convenciones para simplificar la configuración y el despliegue de aplicaciones.

### 2. Creación del Proyecto
Para comenzar, sigue estos pasos:

1. **Genera un nuevo proyecto Spring Boot**:
   - Utiliza la herramienta **Spring Initializr** en línea o tu IDE preferido (como IntelliJ IDEA o Eclipse).
   - Selecciona las siguientes opciones:
     - **Group**: net.codejava
     - **Artifact**: SpringBootHelloWorld
     - **Dependencies**: Elige "Web" para habilitar el manejo de solicitudes HTTP.
     
![Scron 1](https://github.com/JuanDavidGarciaPulido/CVDS_LAB5.1_2024-1/assets/90209924/a3de987c-198b-4fad-9aa0-560a2c8700a1)

2. **Estructura del Proyecto**:
   - Descomprime el archivo descargado en una carpeta.
   - Abre el archivo `pom.xml` y elimina la dependencia `spring-boot-starter-test`.

![Scron 2](https://github.com/JuanDavidGarciaPulido/CVDS_LAB5.1_2024-1/assets/90209924/49f2f2e9-b2e4-4c5e-b0bf-b1940c60f13e)

### 3. Creación del Controlador
1. **Crea un controlador**:
   - Abre la clase `SpringBootHelloWorldApplication.java`.
   - Agrega la anotación `@RestController` a la clase.
   - Crea un método llamado `home()` con la anotación `@RequestMapping("/")` que devuelve un mensaje "Hello world Spring Boot".

![Scron 3](https://github.com/JuanDavidGarciaPulido/CVDS_LAB5.1_2024-1/assets/90209924/0d261d7a-20d6-4376-9359-90fd07627893)

2. **Ejecuta la Aplicación**:
   - Ejecuta la aplicación usando el comando `mvn spring-boot:run`.
   - Accede a ella desde el navegador en [http://localhost:8080/](http://localhost:8080/).

![Scron 4](https://github.com/JuanDavidGarciaPulido/CVDS_LAB5.1_2024-1/assets/90209924/7855e427-e97b-40b1-a58d-9f9005c7797b)

3. **Personalización del Mensaje**:
   - Modifica el método `home()` para usar etiquetas HTML y agrega otro método con `@RequestMapping("/new")` que devuelva otro mensaje.

![Scron 5](https://github.com/JuanDavidGarciaPulido/CVDS_LAB5.1_2024-1/assets/90209924/7a1d586a-ac76-41c6-8c16-11bb1c466928)

### 4. Empaquetado y Ejecución
1. **Empaqueta la Aplicación**:
   - Ejecuta `mvn package` para crear un archivo JAR ejecutable.

![Scron 6](https://github.com/JuanDavidGarciaPulido/CVDS_LAB5.1_2024-1/assets/90209924/b12ca4f5-bb8b-4ed0-acd3-9a057c7c536a)

2. **Ejecuta la Aplicación**:
   - Ejecuta la aplicación con el comando `java -jar target/SpringBootHelloWorld-0.0.1-SNAPSHOT.jar`.

![Scron 7](https://github.com/JuanDavidGarciaPulido/CVDS_LAB5.1_2024-1/assets/90209924/81a3d7b4-416b-4ed0-8f48-5809b953b883)

¡Listo! Ahora tienes un proyecto Spring Boot con un servicio "Hello World".
