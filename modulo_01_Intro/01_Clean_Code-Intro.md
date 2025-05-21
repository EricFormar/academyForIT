# Clean Code

"Clean Code: A Handbook of Agile Software Craftsmanship" es una obra fundamental escrita por Robert C. Martin (también conocido como "Uncle Bob") que revolucionó la forma en que los desarrolladores piensan sobre la calidad del código.

Publicado en 2008, este libro se ha convertido en una referencia esencial para programadores de todos los niveles que buscan mejorar sus habilidades de programación. La premisa central es simple pero poderosa: el código limpio no es solo una cuestión de estética, sino de profesionalismo y eficiencia. Martin argumenta que escribir código limpio es una disciplina y un arte que marca la diferencia entre un buen programador y un gran programador. A través de ejemplos prácticos, casos de estudio y principios concretos, el libro enseña cómo transformar código confuso y desordenado en código elegante y mantenible.

"Clean Code" es parte de la serie de libros de Martin sobre artesanía de software, que promueve la idea de que la programación es una disciplina que requiere dedicación, práctica constante y un compromiso con la excelencia.

Los temas principales incluyen:

- Nombres significativos para variables, funciones y clases
- Diseño de funciones efectivas y concisas
- Comentarios apropiados (y cuándo evitarlos)
- Formato de código para mejorar la legibilidad
- Manejo de errores profesional
- Estructuras de datos y objetos bien diseñados
- Pruebas unitarias y desarrollo guiado por pruebas (TDD)
- Refactorización sistemática

Una vez que hayas leído el libro, respondé el siguiente cuestionario

## Cuestionario 

### Pregunta 1:

Según "Clean Code", ¿cuál es el principal beneficio de usar nombres significativos y pronunciables para variables, funciones y clases?

    ⬜ Mejoran la legibilidad y la mantenibilidad del código, haciendo que el propósito sea claro sin necesidad de comentarios.

    ⬜ Permiten que el compilador de TypeScript genere un código JavaScript más optimizado.

    ⬜ Reducen el número total de líneas de código en el proyecto.

### Pregunta 2:

¿Cuál es la recomendación principal de "Clean Code" sobre la longitud de las funciones?

    ⬜ No deben exceder las 50 líneas de código para facilitar la revisión.

    ⬜ Deben ser lo más pequeñas posible, idealmente haciendo una sola cosa (Principio de Responsabilidad Única a nivel de función).

    ⬜ Su longitud es irrelevante si están bien comentadas.

    ⬜ Deben agrupar lógica relacionada, incluso si eso las hace más largas, para mantener la cohesión.

### Pregunta 3:

    ⬜ Imagina que encuentras el siguiente comentario en el código: // Incrementa el contador. ¿Qué sugiere "Clean Code" sobre este tipo de comentario?

    ⬜ Es un buen comentario porque explica lo que hace el código.

    ⬜ Es redundante y debería eliminarse. El código debería ser autoexplicativo (por ejemplo, usando una variable llamada counter y la operación counter++).

    ⬜ Debería expandirse para incluir por qué se incrementa el contador.

### Pregunta 4:

Dada la importancia de la consistencia en el formato del código, ¿cuál de estas prácticas se alinea mejor con los principios de "Clean Code" para un equipo que usa TypeScript?

    ⬜ Permitir que cada desarrollador use su propio estilo de formato preferido y confiar en los code reviews para unificarlo.

    ⬜ Utilizar herramientas automáticas como Prettier y ESLint con una configuración compartida (.prettierrc, .eslintrc.js) commiteada en el repositorio Git.

    ⬜ Definir manualmente las reglas de formato en un documento Wiki y revisarlas semestralmente.

    ⬜ Priorizar la densidad horizontal del código (más código por línea) para reducir el scrolling vertical.

### Pregunta 5:

````ts
class UserProcessor {
  getUserData(userId: string): User {
    // Lógica para buscar en DB
    return db.findUser(userId);
  }

  validateEmail(email: string): boolean {
    // Lógica de validación de email
    return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
  }

  sendWelcomeEmail(user: User): void {
    // Lógica para enviar email
    emailService.send(user.email, 'Welcome!', '...');
  }

  generateAuthToken(user: User): string {
      // Lógica para generar token JWT
      return jwt.sign({ id: user.id }, SECRET_KEY);
  }
}
````
Considera la siguiente clase de TypeScript. ¿Qué principio de "Clean Code" viola principalmente?

    ⬜ El Principio de Responsabilidad Única (SRP), ya que la clase maneja obtención de datos, validación, envío de emails y generación de tokens.

    ⬜ El Principio Abierto/Cerrado (OCP), porque no se puede extender fácilmente.

    ⬜ La Ley de Demeter (LoD), debido a las llamadas a servicios externos.

### Pregunta 6:

¿Cuál es la diferencia fundamental entre Objetos y Estructuras de Datos según la perspectiva de "Clean Code"?

    ⬜ Los Objetos exponen su comportamiento y ocultan sus datos, mientras que las Estructuras de Datos exponen sus datos y tienen poco o ningún comportamiento.

    ⬜ Los Objetos se usan para lógica de negocio compleja y las Estructuras de Datos para DTOs (Data Transfer Objects) simples.

    ⬜ No hay diferencia significativa en lenguajes como TypeScript donde las clases pueden tener tanto propiedades públicas como métodos.

    ⬜ Las Estructuras de Datos son siempre inmutables, mientras que los Objetos pueden ser mutables.

### Pregunta 7:

En el manejo de errores, ¿qué prefiere generalmente "Clean Code" sobre devolver códigos de error (como null o -1)?

    ⬜ Devolver códigos de error porque son más fáciles de manejar con sentencias if/else.

    ⬜ Devolver códigos de error porque son más fáciles de manejar con sentencias if/else.
    Usar excepciones no comprobadas (unchecked exceptions) para separar la lógica de manejo de errores del flujo principal.

    ⬜ Devolver códigos de error porque son más fáciles de manejar con sentencias if/else.
    Usar excepciones comprobadas (checked exceptions) para forzar al llamador a manejar el error.

    ⬜ Devolver códigos de error porque son más fáciles de manejar con sentencias if/else.
    Registrar el error en consola y devolver un valor por defecto.

### Pregunta 8:

Estás integrando una librería externa de pagos. Según "Clean Code", ¿cuál es la mejor estrategia para interactuar con esta librería dentro de tu aplicación?

    ⬜ Llamar directamente a las funciones de la librería desde tu lógica de negocio donde sea necesario.

    ⬜ Crear una capa de "Adaptador" (Adapter pattern) que envuelva la librería externa, exponiendo una interfaz que controle tu aplicación y oculte los detalles de la librería.

    ⬜ Modificar el código fuente de la librería externa para que se ajuste mejor a las necesidades de tu aplicación.

    ⬜ Asegurarse de que todas las clases que usan la librería la reciban por inyección de dependencias.

### Pregunta 9:

El acrónimo FIRST se usa para describir las cualidades de los buenos tests unitarios en "Clean Code". ¿Qué significa la 'F'?

    ⬜ Fast (Rápidos): Los tests deben ejecutarse rápidamente.

    ⬜ Flexible: Los tests deben adaptarse fácilmente a los cambios.

    ⬜ Focused (Enfocados): Cada test debe probar una sola cosa.

    ⬜ Frequent (Frecuentes): Los tests deben ejecutarse frecuentemente.

### Pregunta 10:

Considera una función processOrder(order: Order, user: User, sendNotification: boolean) en TypeScript. ¿Qué problema potencial señala "Clean Code" sobre esta firma de función?

    ⬜ El uso de tipos (Order, User) es demasiado estricto.

    ⬜ Tiene demasiados argumentos (3). Idealmente, las funciones deberían tener 0, 1 o 2 argumentos.

    ⬜ El argumento booleano (sendNotification) es una "Flag Argument" que sugiere que la función hace más de una cosa (procesa y opcionalmente notifica).

    ⬜ El nombre processOrder es ambiguo.

### Pregunta 11:

    ⬜ ¿Qué es la "Ley de Demeter" (Law of Demeter) o Principio de Menor Conocimiento?

    ⬜ Una ley que obliga a escribir comentarios para cada método público.

    ⬜ Un principio que sugiere que un método de un objeto debe invocar métodos solamente de: el objeto mismo, objetos pasados como parámetros, objetos creados dentro del método, u objetos componentes directos.

    ⬜ Una regla de formato que limita la longitud de las líneas de código.

    ⬜ Un patrón de diseño para manejar dependencias circulares.

### Pregunta 12:

En el contexto de "Clean Code", ¿qué significa el término "Code Smell" (Olor a Código)?

    ⬜ Un error de sintaxis detectado por el compilador de TypeScript.

    ⬜ Código que funciona correctamente pero exhibe características que sugieren un problema más profundo en el diseño (p.ej., funciones muy largas, clases con muchas responsabilidades, código duplicado).

    ⬜ Comentarios obsoletos o incorrectos en el código.

    ⬜ Código que no sigue las guías de estilo del equipo.

### Pregunta 13:

¿Qué postula la "Regla del Boy Scout" aplicada al desarrollo de software?

    ⬜ Siempre planificar detalladamente antes de escribir cualquier código.

    ⬜ Dejar el código un poco más limpio de lo que lo encontraste (p.ej., renombrar una variable, extraer una función pequeña) cada vez que lo tocas.

    ⬜ Escribir tests unitarios para cada nueva funcionalidad antes de implementarla (TDD).

    ⬜ Utilizar siempre los últimos frameworks y tecnologías disponibles.

### Pregunta 14:

Tienes dos funciones en TypeScript que hacen casi lo mismo, pero con pequeñas variaciones. ¿Qué estrategia de refactorización promovería "Clean Code" para abordar esta duplicación?

    ⬜ Mantener ambas funciones separadas si las diferencias son significativas.

    ⬜ Extraer la lógica común a una nueva función privada y llamar a esta desde las dos funciones originales, pasando las diferencias como parámetros.

    ⬜ Copiar y pegar la lógica, modificando ligeramente la copia.

    ⬜ Marcar una de las funciones como obsoleta (@deprecated) y usar solo la otra.

### Pregunta 15:

¿Por qué "Clean Code" aboga por clases pequeñas y con alta cohesión?

    ⬜ Porque las clases pequeñas son más fáciles de entender, testear y mantener, y la alta cohesión asegura que sus responsabilidades estén estrechamente relacionadas.

    ⬜ Porque reduce el acoplamiento entre diferentes módulos del sistema.

    ⬜ Porque permite una mayor reutilización del código a través de la herencia.

    ⬜ Porque mejora el rendimiento en tiempo de ejecución.

### Pregunta 16:

Según Kent Beck, el diseño simple (Simple Design) sigue cuatro reglas en orden de prioridad. ¿Cuál es la primera y más importante regla?

    ⬜ Minimizar el número de clases y métodos.

    ⬜ Pasar todos los tests.

    ⬜ Maximizar la claridad (Revelar la intención).

    ⬜ Eliminar la duplicación (DRY - Don't Repeat Yourself).

### Pregunta 17:

Estás trabajando en un módulo que interactúa con la base de datos. ¿Qué principio de diseño te ayudaría a desacoplar tu lógica de negocio de los detalles específicos de la implementación de la base de datos (p.ej., usar PostgreSQL vs. MongoDB)?

    ⬜ Inyección de Dependencias (DI) y el Principio de Inversión de Dependencias (DIP), usando interfaces o tipos abstractos para definir el contrato del repositorio.

    ⬜ El Principio de Responsabilidad Única (SRP).

    ⬜ El Principio Abierto/Cerrado (OCP).

    ⬜ La Ley de Demeter (LoD).

### Pregunta 18:

¿Cuál es una de las principales críticas o dificultades al aplicar estrictamente TDD (Test-Driven Development) como se sugiere en libros como "Clean Code"?

    ⬜ Requiere escribir más código de producción.

    ⬜ Puede ser difícil escribir tests para funcionalidades complejas o que dependen de sistemas externos (UI, bases de datos) sin un buen diseño o herramientas de mocking.

    ⬜ Los tests resultantes suelen ser frágiles y se rompen con frecuencia.

    ⬜ No es compatible con metodologías ágiles como Scrum.

### Pregunta 19:

Si una función necesita devolver varios datos relacionados, ¿qué alternativa prefiere "Clean Code" en lugar de usar parámetros de salida (out parameters) o devolver un objeto genérico Object?

    ⬜ Devolver un array donde la posición de cada elemento indica qué dato es.

    ⬜ Crear una clase o interfaz específica (por ejemplo, un DTO) que encapsule esos datos con nombres significativos.

    ⬜ Devolver una tupla (tuple) de TypeScript.

    ⬜ Modificar variables globales para almacenar los resultados.

### Pregunta 20:

Al refactorizar código existente para hacerlo "más limpio", ¿cuál es la práctica más importante para asegurar que no se introduzcan regresiones?

    ⬜ Realizar cambios muy grandes de una sola vez para minimizar conflictos.

    ⬜ Tener una suite de tests unitarios robusta que cubra el código antes de empezar a refactorizar, y ejecutarla frecuentemente.

    ⬜ Documentar exhaustivamente cada cambio realizado en los comentarios.

    ⬜ Pedir a otro desarrollador que revise manualmente todo el código modificado.