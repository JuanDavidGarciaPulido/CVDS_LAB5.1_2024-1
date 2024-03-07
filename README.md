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
>>>>>>> d61fa1f0e5debf9841f563ec9a3d7fabe0c75dd3

3. **Personalización del Mensaje**:
   - Modifica el método `home()` para usar etiquetas HTML y agrega otro método con `@RequestMapping("/new")` que devuelva otro mensaje.





=======
![Scron 5](https://github.com/JuanDavidGarciaPulido/CVDS_LAB5.1_2024-1/assets/90209924/7a1d586a-ac76-41c6-8c16-11bb1c466928)


### 4. Empaquetado y Ejecución
1. **Empaqueta la Aplicación**:
   - Ejecuta `mvn package` para crear un archivo JAR ejecutable.




=======
![Scron 6](https://github.com/JuanDavidGarciaPulido/CVDS_LAB5.1_2024-1/assets/90209924/b12ca4f5-bb8b-4ed0-acd3-9a057c7c536a)


2. **Ejecuta la Aplicación**:
   - Ejecuta la aplicación con el comando `java -jar target/SpringBootHelloWorld-0.0.1-SNAPSHOT.jar`.

 

¡Listo! Ahora tienes un proyecto Spring Boot con un servicio "Hello World".


## __Capítulo 3: ´Configuración del CORS en ambos proyectos.__

Como desarrollador fullstack con experiencia en React y Spring Boot, puedo ayudarte a configurar el **Cross-Origin Resource Sharing (CORS)** entre tus proyectos. Aquí tienes un paso a paso para habilitar CORS en un servicio "Hello, World" creado con Spring Boot:

1. **Crear un Proyecto Spring Boot**:
   - Si aún no tienes un proyecto Spring Boot, puedes crear uno utilizando [Spring Initializr](https://start.spring.io/). Asegúrate de incluir la dependencia de **Spring Web**.
   - Alternativamente, puedes descargar el proyecto preconfigurado desde [este repositorio](https://github.com/spring-guides/gs-rest-service-cors).

2. **Agregar la Anotación `@CrossOrigin`**:
   - En tu controlador Spring (donde defines tus endpoints), agrega la anotación `@CrossOrigin` a los métodos que deseas habilitar para CORS.
   - Por ejemplo, si tienes un endpoint `/api/hello`, puedes hacer lo siguiente:

    ```java
    import org.springframework.web.bind.annotation.CrossOrigin;
    import org.springframework.web.bind.annotation.GetMapping;
    import org.springframework.web.bind.annotation.RestController;

    @RestController
    public class HelloController {

        @CrossOrigin
        @GetMapping("/api/hello")
        public String hello() {
            return "¡Hola, Mundo!";
        }
    }
    ```
    ![Scron 8](https://github.com/JuanDavidGarciaPulido/CVDS_LAB5.1_2024-1/assets/90209924/7fd708e8-694d-46f1-86b2-67d5cde27187)


   - La anotación `@CrossOrigin` le indica al navegador que este endpoint es accesible desde cualquier origen.



3. **Configurar Opciones Adicionales (Opcional)**:
   - Puedes personalizar la configuración de CORS agregando más opciones a la anotación `@CrossOrigin`. Por ejemplo:

    ```java
    @CrossOrigin(origins = "http://mi-frontend.com", allowedHeaders = "*", methods = {RequestMethod.GET, RequestMethod.POST})
    ```

   - En este ejemplo, solo se permiten solicitudes desde `http://mi-frontend.com`, se aceptan todos los encabezados y se habilitan los métodos GET y POST.

4. **Prueba tu Servicio**:
   - Inicia tu aplicación Spring Boot y accede al endpoint `/api/hello` desde tu aplicación frontend (por ejemplo, una aplicación React).
   - Deberías poder recibir una respuesta exitosa sin errores de CORS.

¡Listo! Siguiendo estos pasos, habrás configurado correctamente CORS en tu servicio "Hello, World" de Spring Boot. Si tienes alguna pregunta adicional o necesitas más detalles, no dudes en preguntar. 😊
