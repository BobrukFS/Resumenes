# Modelos de datos

Un **modelo de datos** es una serie de conceptos que se utilizan para describir un conjunto de datos y las operaciones para manipularlos.

Hay dos tipos de modelos de datos:

1. **Modelo Conceptual:**
    
    - **Propósito:** El modelo conceptual se centra en representar la estructura y las relaciones de los datos de una manera independiente de la tecnología de base de datos subyacente. Su objetivo principal es capturar las entidades, atributos y relaciones esenciales entre los datos del mundo real.
    - **Enfoque:** Se utiliza para comprender las necesidades de los usuarios y los requisitos de información del sistema. Ayuda a establecer una visión clara de cómo los datos están conectados y qué información se necesita gestionar.
    - **Representación:** Suele usar diagramas, como el Modelo Entidad-Relación (MER), para visualizar las entidades, atributos y relaciones, sin preocuparse por cómo se almacenan físicamente.
    - **Abstracción:** Es más abstracto y no se preocupa por detalles técnicos como índices, claves primarias o optimización de consultas.
    
1. **Modelo Lógico:**
    
    - **Propósito:** El modelo lógico se concentra en cómo los datos se almacenan y manipulan en un sistema de gestión de bases de datos (DBMS) específico. Transforma el modelo conceptual en una estructura de base de datos real y considera las restricciones y características específicas del DBMS.
    - **Enfoque:** Se traduce el modelo conceptual en un conjunto de tablas, columnas y relaciones. También se definen claves primarias, claves foráneas, índices y otros elementos necesarios para implementar la base de datos en un sistema real.
    - **Representación:** Puede expresarse a través de declaraciones SQL (Structured Query Language) o diagramas más detallados que reflejan la estructura física de la base de datos como MR (Modelo relacional) que si es soportado por los DBMS a diferencia del MER.
    - **Abstracción:** Aunque sigue siendo un nivel abstracto en comparación con la implementación física, aborda cuestiones más específicas relacionadas con el almacenamiento y la gestión de datos en el DBMS elegido.
3. **Modelo fisico**: Un modelo físico de una base de datos se refiere a la forma en que se implementa una base de datos en un sistema de almacenamiento físico, como un disco duro o un servidor de bases de datos. Este nivel de diseño se centra en la estructura física de los datos y cómo se almacenan y acceden desde el hardware subyacente.

En el diseño de base de datos se usan primero los modelos conceptuales para lograr una descripcion de alto nivel de la realidad, y luego se transforma al esquema conceptual en un esquema logico.

Un **esquema** es un conjunto de representaciones linguisticas o graficas que describen la estructura de los datos de interes. Los modelos conceptuales deben ser buenas herramientas para representar la realidad, por lo que deben poseer las siguientes cualidades:

* **Expresividad** : Deben tener suficientes conceptos para expresar la realidad.
* **Simplicidad**: Deben ser simples para que los esquemas sean faciles de entender.
* **Minimalidad**: Cada concepto debe tener un significado distinto
* **Formalidad**: Todos los conceptos deben tener una interpretacion unica y precisa.

[[Modelo entidad-relacion]]
[[Modelo relacional]]