# Arquitetura de Software

La arquitectura de software es la estructura subyacente de un sistema de software que define cómo se dividen las responsabilidades entre los componentes y cómo estos componentes se comunican. Su objetivo es garantizar que el sistema sea eficiente, escalable, mantenible y cumpla con los requisitos funcionales y no funcionales.
## Tipos de Arquitectura de Sofware
### Arquitectura Monolitica

Todas las funcionalidades están contenidas en una única aplicación. Fácil de desarrollar y desplegar, pero puede ser difícil de escalar y mantener a medida que crece.

```
- MyApp/
  - src/
    - controllers/
    - models/
    - views/
    - utils/
  - public/
  - config/
  - package.json
  - app.js
```
### Arquitectura Cliente-Servidor
Divide la aplicación en dos partes principales: el cliente (interfaz de usuario) y el servidor (lógica de negocio y datos). Permite la escalabilidad y la distribución de cargas.

```
- MyClient/
  - src/
    - components/
    - views/
  - public/
  - package.json
  - index.html
- MyServer/
  - src/
    - controllers/
    - models/
    - routes/
  - config/
  - package.json
  - server.js
```
### Arquitectura de Microservicios:
Divide la aplicación en múltiples servicios pequeños e independientes, cada uno con su propia lógica de negocio. Facilita la escalabilidad, el despliegue y la independencia de servicios.

```
- Service1/
  - src/
    - controllers/
    - models/
  - config/
  - package.json
  - service.js
- Service2/
  - src/
    - controllers/
    - models/
  - config/
  - package.json
  - service.js
- Service3/
  - src/
    - controllers/
    - models/
  - config/
  - package.json
  - service.js
- Gateway/
  - src/
    - routes/
  - config/
  - package.json
  - gateway.js
```
### Arquitectura Orientada a Servicios (SOA)
Divide la aplicación en servicios reutilizables que se comunican a través de estándares, como SOAP o REST. Promueve la interoperabilidad y la reutilización de servicios.

```
- UserService/
  - src/
    - services/
    - models/
  - config/
  - package.json
  - service.js
- PaymentService/
  - src/
    - services/
    - models/
  - config/
  - package.json
  - service.js
- OrderService/
  - src/
    - services/
    - models/
  - config/
  - package.json
  - service.js
- APIGateway/
  - src/
    - routes/
  - config/
  - package.json
  - gateway.js
```
### Arquitectura de Capas
Organiza la aplicación en capas lógicas, como la capa de presentación, la capa de lógica de negocio y la capa de acceso a datos. Facilita la separación de preocupaciones y la mantenibilidad.

```
- MyApp/
  - PresentationLayer/
    - controllers/
    - views/
  - BusinessLogicLayer/
    - services/
    - models/
  - DataAccessLayer/
    - repositories/
    - models/
  - Infrastructure/
    - utilities/
  - package.json
  - app.js
```
### Arquitectura de Componentes
Divide la aplicación en componentes reutilizables y autocontenidos. Los componentes pueden comunicarse entre sí a través de interfaces definidas.

```
- MyApp/
  - components/
    - component1/
      - src/
      - config/
      - package.json
    - component2/
      - src/
      - config/
      - package.json
  - package.json
  - app.js
```
### Arquitectura basada en Eventos
Los componentes interactúan enviando y recibiendo eventos. Se utiliza en sistemas altamente distribuidos y reactivos.

```
- EventProcessingApp/
  - eventHandlers/
    - eventHandler1/
      - src/
      - config/
      - package.json
    - eventHandler2/
      - src/
      - config/
      - package.json
  - package.json
  - app.js
```
### Arquitectura sin Servidor (Serverless)
Elimina la necesidad de administrar servidores, ya que las funciones son ejecutadas bajo demanda en entornos controlados por el proveedor de servicios en la nube.

```
- ServerlessFunctions/
  - function1/
    - src/
    - serverless.yml
  - function2/
    - src/
    - serverless.yml
  - function3/
    - src/
    - serverless.yml
```
### Arquitectura en la Nube (Cloud-native)
Diseñada específicamente para aprovechar servicios y recursos en la nube. Puede incluir microservicios, contenedores y herramientas específicas de la nube.

```
- CloudNativeApp/
  - services/
    - service1/
      - src/
      - Dockerfile
    - service2/
      - src/
      - Dockerfile
  - containers/
    - nginx/
      - conf/
      - Dockerfile
  - kubernetes/
    - deployment.yaml
  - serverless/
    - function1/
      - src/
      - serverless.yml
  - package.json
  - app.js
```

Estos son ejemplos generales y simplificados. La estructura de carpetas específica puede variar según las necesidades y tecnologías utilizadas en un proyecto real.