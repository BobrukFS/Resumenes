# Caracteristicas basicas de Docker

Docker es una plataforma abierta para desarrollar, enviar y ejecutar aplicaciones. Docker le permite separar sus aplicaciones de su infraestructura para que pueda entregar software rápidamente. Con Docker, puede administrar su infraestructura de la misma manera que administra sus aplicaciones. Al aprovechar las metodologías de Docker para enviar, probar e implementar código, puede reducir significativamente el retraso entre escribir el código y ejecutarlo en producción.

Docker brinda la capacidad de empaquetar y ejecutar una aplicación en un entorno poco aislado llamado contenedor. El aislamiento y la seguridad le permiten ejecutar muchos contenedores simultáneamente en un host determinado. Los contenedores son livianos y contienen todo lo necesario para ejecutar la aplicación, por lo que no es necesario depender de lo que está instalado en el host. Puede compartir contenedores mientras trabaja y asegurarse de que todas las personas con las que comparte obtengan el mismo contenedor que funciona de la misma manera.

Docker proporciona herramientas y una plataforma para gestionar el ciclo de vida de sus contenedores:

- Desarrolle su aplicación y sus componentes de soporte utilizando contenedores.
- El contenedor se convierte en la unidad para distribuir y probar su aplicación.
- Cuando esté listo, implemente su aplicación en su entorno de producción, como un contenedor o un servicio orquestado. Esto funciona igual ya sea que su entorno de producción sea un centro de datos local, un proveedor de nube o un híbrido de ambos.

## Porque usamos Docker

- Desarrollo de aplicaciones: Docker es ampliamente utilizado en el desarrollo de aplicaciones, ya que permite empaquetar una aplicación y sus dependencias en un contenedor aislado. Docker Desktop proporciona una forma sencilla de crear, ejecutar y gestionar contenedores en un entorno de desarrollo local.
    
- Compatibilidad con sistemas operativos: En sistemas operativos Windows y macOS, Docker Desktop permite ejecutar contenedores Linux en un entorno aislado. Esto es útil para desarrolladores que trabajan en sistemas Windows o macOS pero necesitan ejecutar aplicaciones basadas en Linux.
    
- Entornos de desarrollo consistentes: Docker Desktop ayuda a garantizar que los entornos de desarrollo sean consistentes en todo el equipo de desarrollo. Puedes definir las dependencias de tu aplicación en un archivo Dockerfile y asegurarte de que todos los miembros del equipo tengan un entorno de desarrollo idéntico.
    
- Fácil gestión de contenedores: Docker Desktop proporciona una interfaz gráfica que facilita la gestión de contenedores, imágenes y redes. Esto es útil para usuarios que prefieren una experiencia más visual o que no están familiarizados con la línea de comandos de Docker.
    
- Integración con herramientas de desarrollo: Docker Desktop se integra con muchas herramientas de desarrollo populares, lo que facilita la incorporación de Docker en tus flujos de trabajo de desarrollo, como Docker Compose para definir entornos de varias aplicaciones y Kubernetes para orquestación de contenedores.
