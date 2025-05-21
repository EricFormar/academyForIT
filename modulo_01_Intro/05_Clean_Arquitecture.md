# Clean Architecture

"Clean Architecture: A Craftsman's Guide to Software Structure and Design" es una obra fundamental escrita por el legendario ingeniero de software Robert C. Martin, conocido como "Uncle Bob". El libro presenta un conjunto de principios y prácticas para crear sistemas de software robustos, mantenibles y escalables. Martin destila décadas de experiencia en esta guía que trasciende tecnologías específicas para enfocarse en los fundamentos atemporales del buen diseño arquitectónico.

Publicado en el 2017, este libro no es solo un manual técnico, sino una filosofía de diseño que invita a los desarrolladores a pensar críticamente sobre cómo estructuran sus sistemas. Martin utiliza ejemplos claros y analogías efectivas para ilustrar sus puntos, haciendo que conceptos complejos sean accesibles y aplicables en la práctica diaria del desarrollo de software.

Esta obra se ha convertido en una referencia imprescindible para quienes buscan comprender los principios fundamentales de la arquitectura de software más allá de las modas y tendencias pasajeras.

Conceptos clave que aborda el libro

- La importancia de la separación de preocupaciones y la independencia de los detalles
- Principios SOLID para un diseño orientado a objetos efectivo
- La arquitectura en capas y la inversión de dependencias
- Estrategias para manejar la complejidad y el cambio en sistemas grandes
- La relación entre arquitectura y pruebas automatizadas
- Cómo estructurar aplicaciones para facilitar la evolución y el mantenimiento
- La importancia de la comunicación y la colaboración en equipos de desarrollo
- La influencia de la arquitectura en la calidad del software y la satisfacción del cliente

"Clean Architecture" está dirigido a:

- Arquitectos de software
- Desarrolladores que aspiran a diseñar sistemas de mayor escala
- Líderes técnicos que necesitan tomar decisiones estructurales robustas
- Profesionales interesados en prácticas de diseño que resistan la prueba del tiempo

Una vez que hayas leído el libro, respondé el siguiente cuestionario

## Cuestionario

### Pregunta 1:

¿Cuál es el principio fundamental de la Regla de Dependencia en Clean Architecture?

    ⬜ Las capas externas deben depender de las capas internas.

    ⬜ Las dependencias del código fuente solo pueden apuntar hacia adentro, hacia políticas de más alto nivel.

    ⬜ Los frameworks y la base de datos dictan las dependencias de los casos de uso.

### Pregunta 2:

En Clean Architecture, ¿dónde residen las reglas de negocio más importantes y de más alto nivel de la aplicación?

    ⬜ En los Controladores (Interface Adapters).

    ⬜ En las Entidades (Entities).

    ⬜ En los Presentadores (Interface Adapters).

    ⬜ En la capa de UI (Frameworks & Drivers).

### Pregunta 3:

El Principio de Inversión de Dependencias (DIP) establece que:

    ⬜ Los módulos de alto nivel deben depender directamente de los módulos de bajo nivel.

    ⬜ Las abstracciones deben depender de los detalles.

    ⬜ Los módulos de alto nivel no deben depender de los módulos de bajo nivel. Ambos deben depender de abstracciones. Las abstracciones no deben depender de los detalles. Los detalles deben depender de las abstracciones.

### Pregunta 4:

```typescript	
interface IDatabase {
  saveOrder(order: any): void;
}

class MySQLDatabase implements IDatabase {
  saveOrder(order: any): void {
    // Lógica específica de MySQL
    console.log("Order saved to MySQL", order);
  }
}

class OrderProcessor {
  constructor(private db: IDatabase) {}

  process(order: any): void {
    // Lógica de procesamiento
    this.db.saveOrder(order);
  }
}
```
Considera el siguiente código TypeScript. ¿Qué principio SOLID se viola principalmente si OrderProcessor dependiera directamente de MySQLDatabase en lugar de IDatabase?

    ⬜ Principio de Responsabilidad Única (SRP)

    ⬜ Principio Abierto/Cerrado (OCP)

    ⬜ Principio de Inversión de Dependencias (DIP)

### Pregunta 5:

¿Cuál es el propósito principal de la capa de "Casos de Uso" (Use Cases / Interactors)?

    ⬜ Gestionar la interfaz de usuario y la interacción con el usuario.

    ⬜ Contener las reglas de negocio específicas de la aplicación y orquestar el flujo de datos hacia y desde las entidades.

    ⬜ Adaptar los datos del formato de los casos de uso al formato del framework o la base de datos.

    ⬜ Definir los objetos de negocio centrales y sus reglas críticas.

### Pregunta 6:

Según Clean Architecture, ¿qué característica NO es deseable para las Entidades?

    ⬜ Contener la lógica de negocio más general y de más alto nivel.

    ⬜ Ser independientes de los cambios en las capas externas (UI, base de datos, frameworks).

    ⬜ Depender directamente de un ORM específico para la persistencia.

### Pregunta 7:

El concepto de "Screaming Architecture" (Arquitectura Estridente) implica que:

    ⬜ La estructura del proyecto debe revelar inmediatamente el framework web utilizado (ej. Express, NestJS).

    ⬜ La estructura del proyecto debe comunicar claramente el propósito o dominio de la aplicación, no los frameworks o herramientas utilizados.

    ⬜ Se deben utilizar nombres de clases y métodos muy descriptivos y extensos.

### Pregunta 8:

¿Qué son los "Interface Adapters" en el contexto de Clean Architecture?

    ⬜ Son el núcleo de la lógica de negocio de la aplicación.

    ⬜ Son un conjunto de clases que convierten datos desde el formato más conveniente para los casos de uso y entidades, al formato más conveniente para alguna agencia externa como la Base de Datos o la Web.

    ⬜ Son las herramientas, frameworks y la base de datos.

### Pregunta 9:

¿Cuál es una de las principales ventajas de mantener la base de datos como un "detalle" en la capa más externa?

    ⬜ Permite que las consultas a la base de datos sean más rápidas.

    ⬜ Facilita el acoplamiento directo de las reglas de negocio con el esquema de la base de datos para mayor eficiencia.

    ⬜ Permite que el sistema sea independiente del motor de base de datos, facilitando su reemplazo o la postergación de su elección.

    ⬜ Asegura que la base de datos sea el componente más estable del sistema.

### Pregunta 10:

El patrón "Humble Object" se utiliza para:

    ⬜ Hacer que los objetos de la interfaz de usuario sean lo más simples posible, delegando toda la lógica a los presentadores.

    ⬜ Separar el comportamiento difícil de probar (ej. interacción con UI o BD) del comportamiento fácil de probar (lógica pura), moviendo la lógica a un objeto "no humilde" y dejando al objeto "humilde" con la mínima lógica posible.

    ⬜ Minimizar la cantidad de código en los casos de uso.

### Pregunta 11:

¿Cómo se cruzan los límites entre capas según Clean Architecture?

    ⬜ Mediante llamadas directas a funciones de capas internas desde capas externas, pasando objetos complejos del framework.

    ⬜ Utilizando el Principio de Inversión de Dependencias, donde las capas internas definen interfaces que las capas externas implementan, y los datos se transfieren como estructuras de datos simples o DTOs.

    ⬜ Las capas externas exponen APIs que las capas internas consumen.

### Pregunta 12:

Si estás diseñando un sistema de gestión de inventario, ¿cuál de las siguientes afirmaciones se alinea MEJOR con los principios de Clean Architecture sobre las Entidades?

    ⬜ La entidad Product debe tener métodos como saveToDatabase() y sendProductNotificationEmail().

    ⬜ La entidad Product debe contener propiedades como id, name, stockQuantity y lógica de negocio pura como canBeShipped() basada en su estado, pero no cómo se persiste o se notifica.

    ⬜ La entidad Product debe ser una clase generada automáticamente por un ORM para mapear directamente a una tabla products.

### Pregunta 13:

El Principio Abierto/Cerrado (OCP) sugiere que las entidades de software (clases, módulos, funciones) deben estar:

    ⬜ Abiertas para modificación, pero cerradas para extensión.

    ⬜ Abiertas para extensión, pero cerradas para modificación.

    ⬜ Completamente cerradas a cualquier cambio una vez desplegadas.

### Pregunta 14:

¿Qué es el "Componente Principal" (Main Component) en Clean Architecture?

    ⬜ El componente que contiene la lógica de negocio más crítica.

    ⬜ Es el punto de partida de la aplicación, el nivel más bajo y "sucio", responsable de crear, ensamblar y conectar todos los demás componentes y dependencias.

    ⬜ El componente de interfaz de usuario más visible para el usuario.

    ⬜ Un alias para la capa de Casos de Uso.

### Pregunta 15:

Un desarrollador decide que los Casos de Uso en su aplicación TypeScript deben importar directamente módulos de un framework de base de datos específico (ej. TypeORM) para simplificar las operaciones CRUD. ¿Qué implicación tiene esta decisión según Clean Architecture?

    ⬜ Es una buena práctica porque reduce la cantidad de código de abstracción (interfaces, adaptadores).

    ⬜ No tiene mayores implicaciones siempre y cuando la lógica de negocio se mantenga separada.

    ⬜ Viola la Regla de Dependencia, acoplando la lógica de negocio (Casos de Uso) a un detalle de implementación (framework de BD), lo que dificulta la mantenibilidad y el cambio de tecnología de persistencia.

### Pregunta 16:

¿Cuál de los siguientes NO es un principio de cohesión de componentes discutido por Robert C. Martin?

    ⬜ Principio de Reutilización Equivalente (REP - Reuse/Release Equivalence Principle)

    ⬜ Principio de Cierre Común (CCP - Common Closure Principle)

    ⬜ Principio de Dependencia Estable (SDP - Stable Dependencies Principle)

    ⬜ Principio de Reutilización Común (CRP - Common Reuse Principle)

### Pregunta 17:

Al diseñar una API, un Presentador recibe datos de un Caso de Uso y debe formatearlos para una respuesta HTTP. ¿Cuál es la responsabilidad principal del Presentador en este escenario?

    ⬜ Decidir si el usuario está autorizado para realizar la acción (lógica de negocio).

    ⬜ Transformar los datos del modelo de dominio (independiente del framework) a un ViewModel o DTO específico para la respuesta HTTP, sin contener lógica de negocio.

    ⬜ Interactuar directamente con la base de datos para obtener información adicional necesaria para la respuesta.

    ⬜ Contener la lógica de cómo se construye la conexión HTTP y se gestionan los encabezados.

### Pregunta 18:

¿Qué significa que una arquitectura debe ser "independiente del framework"?

    ⬜ Que no se debe usar ningún framework en el proyecto.

    ⬜ Que la arquitectura no debe depender de las particularidades de un framework específico, permitiendo que el framework sea un detalle que se pueda cambiar o actualizar sin reescribir la lógica de negocio.

    ⬜ Que los frameworks solo deben usarse para la capa de UI.

### Pregunta 19:

Considera el siguiente escenario: tienes una clase UserService que maneja la creación de usuarios y el envío de correos de bienvenida. ¿Qué principio SOLID está potencialmente violando UserService?

    ⬜ Principio de Responsabilidad Única (SRP)

    ⬜ Principio de Sustitución de Liskov (LSP)

    ⬜ Principio de Segregación de Interfaces (ISP)

### Pregunta 20:

En el contexto de los límites arquitectónicos, ¿cuál es el principal problema de pasar objetos de Entidad directamente a la capa de Presentación (UI)?

    ⬜ No hay ningún problema, simplifica el código al no necesitar DTOs.

    ⬜ La UI podría depender de campos o métodos de la Entidad que no son necesarios para la vista, o peor aún, podría intentar modificar la Entidad, violando la dirección de las dependencias y acoplando la UI a la lógica de negocio central.

    ⬜ Las Entidades suelen ser demasiado grandes y ralentizan el renderizado de la UI.

    ⬜ Mejora el rendimiento al evitar la creación de objetos intermedios.