# Aplicación "juice-shop"

## Definición de la Aplicación
OWASP Juice Shop es probablemente la aplicación web insegura más moderna y sofisticada que existe. Puede ser utilizada en entrenamientos de seguridad, demostraciones de concienciación, CTFs y como conejillo de indias para herramientas de seguridad. Juice Shop abarca vulnerabilidades de todo el OWASP Top Ten junto con muchas otras vulnerabilidades encontradas en aplicaciones del mundo real.
Este proyecto tiene como objetivo aplicar el S-SDLC y DevSecOps para mitigar estas vulnerabilidades del Top Ten de OWASP, garantizando así un desarrollo seguro y una mayor protección contra posibles ataques.



## Cómo Ejecutar la Aplicación
1.	Instalar Docker
2.	Ejecutar docker pull bkimminich/juice-shop
3.	Ejecutar docker run --rm -p 3000:3000 bkimminich/juice-shop
4.	Navegar a http://localhost:3000 (en macOS y Windows navegar a http://192.168.99.100:3000 si estás utilizando docker-machine en lugar de la instalación nativa de Docker)



## Consideraciones de Seguridad
Juice Shop es conocida por tener varias vulnerabilidades, algunas de las cuales son:
1.	Inyección de código SQL: Juice Shop es vulnerable a ataques de inyección SQL, lo que permite a un atacante ejecutar consultas maliciosas en la base de datos.
2.	Cross-Site Scripting (XSS): La aplicación es susceptible a ataques XSS, lo que permite a los atacantes inyectar scripts maliciosos en las páginas web vistas por otros usuarios.
3.	Inyección de comandos: Juice Shop puede ser vulnerable a la inyección de comandos, lo que permite a un atacante ejecutar comandos arbitrarios en el servidor.
4.	Fuga de información sensible: La aplicación puede filtrar información sensible, como nombres de usuario, contraseñas u otra información confidencial, a través de errores de configuración o de código.

Para mitigar estas vulnerabilidades, se implementarán las siguientes medidas:
1.	Validación de entrada y parámetros de consulta: Validar y escapar correctamente los datos de entrada del usuario para prevenir inyecciones de SQL y XSS.
2.	Sanitización de entrada: Sanitizar cualquier entrada de usuario antes de ejecutar comandos en el servidor para prevenir la inyección de comandos.
3.	Configuración de seguridad adecuada: Asegurarse de que la configuración del servidor esté correctamente protegida y que no se filtre información sensible inadvertidamente.
4.	Actualización de dependencias: Mantener actualizadas las dependencias de la aplicación para parchear las vulnerabilidades conocidas.

El uso de Docker puede ayudar a mitigar algunas de estas vulnerabilidades al proporcionar un entorno controlado y aislado para ejecutar la aplicación. Por ejemplo, Docker puede ayudar a limitar el impacto de las inyecciones de código SQL y de comandos al aislar la aplicación en contenedores. Además, al actualizar las imágenes de Docker con regularidad, se pueden incluir las últimas correcciones de seguridad para las dependencias de Juice Shop, lo que ayuda a mantener la aplicación segura frente a nuevas amenazas.



## Paso a Paso para Crear la Aplicación (S-SDLC)
Para crear el proyecto del Juice Shop desplegado en Docker siguiendo el Secure Software Development Lifecycle (S-SDLC), se deben seguir los siguientes pasos:

### 1. Recopilación de Requisitos

Definición de los Requisitos de la Aplicación:
- Identificar y documentar las funcionalidades esenciales de la aplicación, incluyendo la gestión de usuarios, la visualización de productos y el proceso de compra.
- Establecer requisitos de rendimiento, seguridad y usabilidad para garantizar una experiencia óptima para el usuario.

Análisis de Riesgos:
- Identificar posibles amenazas y vulnerabilidades asociadas con la aplicación.
- Realizar un análisis de riesgos exhaustivo y desarrollar estrategias para mitigarlos.

### 2.  Diseño del Sistema

Diseño de la Arquitectura:
- Establecer la estructura de directorios, modelos de datos y rutas necesarias para la aplicación.
- Definir la arquitectura de la aplicación, incluyendo la elección de un patrón de diseño apropiado como MVC.

Medidas de Seguridad:
- Implementar mecanismos de autenticación y autorización para controlar el acceso a las funcionalidades sensibles.
- Encriptar datos sensibles y aplicar medidas de protección contra vulnerabilidades comunes como XSS y CSRF.

### 3. Implementación

Configuración del Entorno de Desarrollo:
- Instalar y configurar las herramientas necesarias, como Node.js, Express.js y la base de datos correspondiente.
- Configurar el entorno de desarrollo para facilitar el desarrollo y la depuración de la aplicación.

Desarrollo de Funcionalidades:
- Escribir código para implementar las funcionalidades requeridas, como la gestión de usuarios, la navegación por el catálogo de productos y la finalización de pedidos.
- Implementar controles de validación y manejo de errores para garantizar la integridad y seguridad de los datos.

Seguridad en la Implementación:
- Aplicar prácticas de programación segura, como la sanitización de entradas y la prevención de vulnerabilidades de inyección.

### 4. Pruebas

Pruebas Unitarias:
- Desarrollar pruebas unitarias para cada componente de la aplicación, verificando su funcionamiento individual.
- Garantizar que todas las funciones cumplan con los requisitos y manejen adecuadamente casos límite.

Pruebas de Integración:
- Realizar pruebas de integración para asegurar la interoperabilidad entre los diferentes módulos de la aplicación.
- Verificar que la comunicación entre el front-end y el back-end funcione correctamente.

Pruebas de Seguridad:
- Ejecutar pruebas de seguridad, como análisis estático de código y pruebas de penetración, para identificar y corregir posibles vulnerabilidades.

### 5. Despliegue

Configuración del Entorno de Producción:

- Configurar un entorno de producción seguro, utilizando protocolos de comunicación cifrados como HTTPS y certificados SSL.
- Implementar medidas de seguridad adicionales, como firewalls y restricciones de acceso.

Despliegue de la Aplicación:
- Empaquetar la aplicación en contenedores Docker para facilitar su despliegue y escalabilidad.
- Utilizar herramientas como Docker Compose para gestionar y orquestar los contenedores en el entorno de producción.

### 6. Mantenimiento

Gestión de Versiones y Actualizaciones:
- Mantener un control de versiones utilizando sistemas de control de versiones como Git.
- Aplicar actualizaciones y correcciones de seguridad de manera regular para mantener la aplicación protegida contra las últimas amenazas.

Monitorización y Registro:
- Implementar sistemas de monitorización para supervisar el rendimiento y la disponibilidad de la aplicación en tiempo real.
- Configurar registros detallados para registrar eventos y alertas, facilitando la detección temprana de problemas y actividades sospechosas.



## Paso a Paso para Crear la Aplicación (DevSecOps)

Para crear el proyecto del Juice Shop desplegado en Docker aplicando DevSecOps, se deben seguir los siguientes pasos:

### 1. Integración de Seguridad desde el Inicio

Incorporar Pruebas de Seguridad desde el Comienzo del Proyecto:
- Integrar herramientas de análisis estático de código (SAST) en el proceso de desarrollo para identificar posibles vulnerabilidades en el código fuente.
- Implementar pruebas de seguridad automatizadas en el pipeline de integración continua para detectar vulnerabilidades en cada iteración del desarrollo.

### 2. Automatización de Pruebas de Seguridad

Desarrollar Pruebas de Seguridad Automatizadas:
- Crear pruebas automatizadas que evalúen la seguridad de la aplicación en todas las etapas del ciclo de vida del desarrollo.
- Utilizar herramientas de análisis dinámico de seguridad (DAST) para realizar pruebas de penetración automatizadas y encontrar vulnerabilidades en tiempo de ejecución.

### 3. Implementación de Controles de Seguridad

Integrar Controles de Seguridad en el Proceso de Despliegue:
- Configurar herramientas de escaneo de contenedores para identificar vulnerabilidades en las imágenes Docker antes de desplegarlas en producción.
- Utilizar políticas de seguridad basadas en código para garantizar que las configuraciones de seguridad sean consistentes en todos los entornos de implementación.

### 4. Monitoreo Continuo de Seguridad

Establecer Monitoreo Continuo de Seguridad:
- Implementar sistemas de monitoreo de seguridad en tiempo real para detectar y responder rápidamente a posibles amenazas.
- Configurar alertas automatizadas que notifiquen al equipo de desarrollo sobre posibles brechas de seguridad o actividades sospechosas.

### 5. Retroalimentación y Mejora Continua

Fomentar la Retroalimentación y la Mejora Continua:
- Realizar revisiones periódicas de seguridad para evaluar el estado actual de la aplicación y identificar áreas de mejora.
- Utilizar métricas de seguridad para medir el rendimiento del equipo en la gestión de vulnerabilidades y la implementación de controles de seguridad.

### 6. Colaboración entre Equipos

Promover la Colaboración entre Equipos de Desarrollo y Operaciones:
- Establecer un enfoque de trabajo colaborativo entre los equipos de desarrollo, operaciones y seguridad para garantizar una implementación eficaz de DevSecOps.
- Facilitar la comunicación y el intercambio de conocimientos entre los equipos para fomentar una cultura de seguridad en toda la organización.

Al seguir estos pasos y aplicar los principios de DevSecOps, se puede garantizar que el proyecto del Juice Shop desplegado en Docker se desarrolle de manera segura y se mantenga protegido contra amenazas de seguridad en todo momento.


## Evaluación de seguridad mediante herramientas automáticas

### Análisis estático

#### 1. Nodejsscan:

- **Descripción:** Nodejsscan es una herramienta de análisis estático diseñada para identificar vulnerabilidades en aplicaciones Node.js.
- **Motivo de selección:** Dada la naturaleza de Juice-Shop, una aplicación construida sobre Node.js, Nodejsscan es ideal para identificar problemas de seguridad específicos de este entorno.

#### 2. SonarQube:

- **Descripción:** SonarQube es una plataforma de inspección continua de código que realiza análisis estáticos para detectar bugs, vulnerabilidades y deuda técnica.
- **Motivo de selección:** SonarQube proporciona una visión profunda de la calidad del código y es altamente configurable, lo que lo hace adecuado para proyectos de cualquier tamaño.

### Análisis dinámico

#### 1. OWASP ZAP (Zed Attack Proxy):

- **Descripción:** OWASP ZAP es una herramienta de seguridad integrada para encontrar vulnerabilidades en aplicaciones web durante su ejecución.
- **Motivo de selección:** ZAP es ampliamente reconocida y utilizada en la comunidad de seguridad por su capacidad para realizar pruebas de penetración automatizadas y manuales.

### Análisis de imágenes Docker

#### 1. Docker Scout:

- **Descripción:** Docker Scout es una herramienta de análisis de seguridad que escanea imágenes Docker en busca de vulnerabilidades conocidas.
- **Motivo de selección:** Docker Scout permite identificar y mitigar riesgos en las imágenes Docker, asegurando que las aplicaciones desplegadas en contenedores sean seguras.

### Justificación de las herramientas seleccionadas

Las herramientas seleccionadas para esta evaluación de seguridad fueron escogidas debido a sus capacidades específicas y su relevancia en el contexto de Juice-Shop:

- Nodejsscan y SonarQube fueron seleccionadas para el análisis estático debido a su habilidad para examinar el código fuente sin ejecutarlo, proporcionando una visión temprana de posibles vulnerabilidades y malas prácticas de codificación.
- OWASP ZAP fue elegido para el análisis dinámico porque permite interactuar con la aplicación en tiempo real, detectando vulnerabilidades que sólo pueden ser identificadas cuando la aplicación está en funcionamiento.
- Docker Scout se utilizó para el análisis de imágenes Docker, ya que es crucial asegurar que las imágenes contenedorizadas, como las usadas en Juice-Shop, no contengan vulnerabilidades conocidas que puedan ser explotadas.

### Resultados de seguridad y vulnerabilidades conocidas

El uso de estas herramientas permitió obtener una visión integral de las vulnerabilidades presentes en Juice-Shop:

- Nodejsscan identificó múltiples vulnerabilidades de inyección SQL, validación de entrada deficiente y problemas relacionados con la seguridad de las dependencias.
- SonarQube destacó varias áreas con código no seguro, problemas de calidad del código y posibles fallos que podrían llevar a vulnerabilidades de seguridad.
- OWASP ZAP detectó vulnerabilidades de seguridad en la aplicación en ejecución, incluyendo la inyección SQL y la exposición de datos sensibles.
- Docker Scout reveló que las imágenes Docker utilizadas contenían varias vulnerabilidades conocidas, lo que resaltó la necesidad de mantener las imágenes actualizadas y aplicar parches de seguridad.

En resumen, esta evaluación de seguridad automatizada identificó una serie de vulnerabilidades críticas en Juice-Shop, proporcionando una base sólida para mejorar la seguridad de la aplicación y reducir los riesgos asociados.

### Problemas encontrados

Durante el desarrollo de la última tarea, se encontraron algunos problemas que merecen ser destacados:

- Aunque se consiguió exitosamente desplegar la herramienta **Clair**, una plataforma de análisis de seguridad de imágenes Docker, se encontró un error al intentar escanear la imagen de Juice-Shop. Clair alertó del siguiente error:
`[CRIT] ▶ Could not analyze layer: Clair responded with a failure: Got response 400 with message {"Error":{"Message":"could not find layer"}}` Este problema está tipificado en la sección de Troubleshooting de Clair y, aunque no parece ser grave, se pretende solucionar para futuras entregas. Clair es una herramienta poderosa para la detección de vulnerabilidades en imágenes Docker y su integración exitosa mejorará significativamente las capacidades de análisis de seguridad.
- Espacio insuficiente en la VM Debian 12: Inicialmente configurada con 32 GB de almacenamiento, esta VM resultó insuficiente para manejar todas las herramientas y operaciones requeridas, lo que llevó a su fallo y a la necesidad de crear una nueva VM con 75 GB de almacenamiento, resultando en una pérdida de tiempo significativa.




