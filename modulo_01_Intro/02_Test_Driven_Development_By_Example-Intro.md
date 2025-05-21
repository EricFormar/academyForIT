# Test Driven Development By Example

"Test Driven Development by Example" es un libro fundamental escrito por Kent Beck, uno de los pioneros de las metodologías ágiles y creador de Extreme Programming (XP), que transformó radicalmente cómo los desarrolladores abordan la creación de software.

Publicado en 2002, este libro se ha establecido como un recurso indispensable para programadores que buscan mejorar la calidad y confiabilidad de su código. La premisa central es revolucionaria pero pragmática: escribir pruebas antes que el código de producción conduce a mejor diseño y mayor calidad.

Beck presenta el Test Driven Development (TDD) no solo como una técnica de pruebas, sino como una metodología completa de desarrollo que impulsa un diseño emergente y una codificación más enfocada. A través de ejemplos concretos, ejercicios prácticos y explicaciones claras, el libro muestra cómo implementar TDD en situaciones reales.

El libro no se limita a presentar teoría, sino que muestra el proceso de TDD en acción a través de ejemplos detallados, incluyendo la implementación de un framework de pruebas y un sistema de manejo de dinero multicurrencia. Beck comparte insights valiosos acumulados durante años de práctica y enseñanza.

"Test Driven Development by Example" es parte del legado de Beck en el movimiento de desarrollo ágil, que promueve prácticas adaptativas, enfocadas en las personas y orientadas a entregar valor de forma continua e incremental.

Los temas principales incluyen:

- El ciclo rojo-verde-refactorizar (escribir una prueba que falla, implementar código que la pase, - mejorar el código)
- Patrones para escribir pruebas efectivas
- Estrategias para refactorización segura
- Desarrollo incremental orientado por pruebas
- Implementación de diferentes tipos de pruebas unitarias
- Gestión de dependencias en pruebas
- Uso de TDD para resolver problemas complejos
- Integración de TDD en el flujo de trabajo cotidiano

Una vez que hayas leído el libro, respondé el siguiente cuestionario

## Cuestionario

### Pregunta 1:

Según Kent Beck en "Test Driven Development By Example", ¿cuál es el objetivo principal de TDD?

    ⬜ Minimizar el número de líneas de código escritas.

    ⬜ Eliminar el miedo durante el desarrollo de software.

    ⬜ Asegurar que todo el código sea refactorizado continuamente, sin importar los tests.

    ⬜ Reducir la necesidad de comunicación dentro del equipo de desarrollo.

### Pregunta 2:

¿Cuál es la secuencia correcta del ciclo de TDD (Red-Green-Refactor)?

    ⬜ Refactorizar -> Escribir test que falla -> Hacer que el test pase.


    ⬜ Escribir test que falla -> Hacer que el test pase -> Refactorizar.

    ⬜ Hacer que el test pase -> Escribir test que falla -> Refactorizar.

    ⬜ Refactorizar -> Hacer que el test pase -> Escribir test que falla.

### Pregunta 3:

En el paso 'Red' del ciclo TDD, ¿qué tipo de fallo se busca idealmente?

    ⬜ Un fallo de compilación que impida la ejecución del programa.

    ⬜ Una excepción en tiempo de ejecución debido a una lógica incorrecta.

    ⬜ Una aserción fallida (assertion failure) que demuestre la ausencia de la funcionalidad deseada.

    ⬜ Un bucle infinito que congele el sistema.

### Pregunta 4:

¿Qué se entiende por 'Fake It' como una estrategia para hacer pasar un test rápidamente en el paso 'Green'?

    ⬜ Escribir la implementación completa y correcta de inmediato.

    ⬜ Retornar un valor constante o una implementación mínima que haga pasar el test, para luego refactorizar.

    ⬜ Usar un mock object complejo que simule todo el comportamiento.

### Pregunta 5:

Cuando Kent Beck habla de 'Triangulation' en TDD, ¿a qué se refiere?

    ⬜ Crear tres tests diferentes que validen la misma funcionalidad.

    ⬜ Generalizar el código solo cuando dos o más ejemplos (tests) demanden una solución más abstracta.

    ⬜ Definir tres capas de abstracción en el diseño del software.

    ⬜ Dividir un test complejo en tres tests más pequeños.

### Pregunta 6:

¿Por qué se enfatiza la velocidad de ejecución de los tests unitarios en TDD?

    ⬜ Para poder integrarlos fácilmente en un pipeline de Continuous Integration.

    ⬜ Para que el desarrollador pueda ejecutarlos con frecuencia, obteniendo retroalimentación rápida.

    ⬜ Para reducir el consumo de recursos de la máquina de desarrollo.

### Pregunta 7:

Cuál de las siguientes afirmaciones no es una característica de un buen test unitario según TDD:

    ⬜ Deben ser rápidos.

    ⬜ Deben ser independientes entre sí.

    ⬜ Deben ser ortogonales (probar diferentes aspectos).

    ⬜ Deben depender del orden de ejecución para asegurar la cobertura total.

### Pregunta 8:

Kent Beck sugiere que una de las formas de manejar el miedo en el desarrollo es:

    ⬜ Evitar la retroalimentación para no desmoralizarse.

    ⬜ Comenzar con la solución más compleja para demostrar habilidad.

    ⬜ Aprender concretamente lo más rápido posible, a través de tests.

    ⬜ Trabajar en aislamiento para evitar distracciones.

### Pregunta 9:

Considerando el siguiente test en TypeScript, ¿qué se espera en el paso 'Red' si add aún no está implementado?

    ⬜ Un error de tipo (TypeScript compile error) indicando que add no existe.

    ⬜ Un ReferenceError en tiempo de ejecución si add no se ha declarado.

    ⬜ Un fallo de aserción (e.g., expect(calculator.add(1, 2)).toBe(3)) porque el valor retornado no es el esperado (o add retorna undefined/null).

    ⬜ El test pasará accidentalmente, indicando un test mal diseñado.

### Pregunta 10:

Según el libro, ¿cuál es el propósito de la fase de 'Refactor' en TDD?

    ⬜ Añadir nuevas funcionalidades que no estaban cubiertas por los tests.

    ⬜ Optimizar el rendimiento del código a toda costa.

    ⬜ Eliminar duplicación, mejorar la legibilidad y la estructura del código, manteniendo los tests en verde.

    ⬜ Reescribir completamente el código cada vez que se detecta un smell.

### Pregunta 11:

¿Por qué es importante tener una 'lista de tests' antes o durante el ciclo de TDD?

    ⬜ Para asegurar que todos los desarrolladores trabajen en el mismo test simultáneamente.

    ⬜ Para tener un registro exhaustivo de todos los posibles bugs del sistema.

    ⬜ Para guiar el desarrollo, asegurando que se cubran los diferentes escenarios y funcionalidades, y para no olvidar ideas de tests o refactorings.

    ⬜ Es una práctica obsoleta que solo añade burocracia.

### Pregunta 12:

Si un test unitario es 'frágil', ¿qué implicación de diseño puede sugerir según Beck?

    ⬜ Que el test tiene demasiadas aserciones.

    ⬜ Que una parte de la aplicación está afectando sorprendentemente a otra, indicando un acoplamiento inesperado.

    ⬜ Que se está utilizando una librería de testing incorrecta.

    ⬜ Que el desarrollador está utilizando una versión de Node.js incompatible.

### Pregunta 13:

¿Qué significa el principio de 'Clean Code That Works' en el contexto de TDD?

    ⬜ Priorizar la belleza del código sobre su funcionalidad.

    ⬜ Escribir código funcional y elegante que esté respaldado por tests automatizados.

    ⬜ Ignorar la limpieza del código siempre y cuando los tests pasen.

    ⬜ Es un objetivo inalcanzable en la mayoría de los proyectos.

### Pregunta 14:

Al escribir un test, ¿cuál es la primera parte que Kent Beck sugiere escribir?

    ⬜ El setup de los objetos necesarios.

    ⬜ La aserción (e.g., expect(...)).

    ⬜ La llamada al método bajo prueba.

    ⬜ Los comentarios explicando el propósito del test.

### Pregunta 15:

Un beneficio clave de TDD es que ayuda a los desarrolladores a enfocarse en:

    ⬜ La implementación de detalles de bajo nivel antes que la funcionalidad.

    ⬜ Los requisitos y la interfaz de la funcionalidad antes de escribir el código de producción.

    ⬜ Cómo optimizar la base de datos desde el principio.

    ⬜ Diseñar la arquitectura completa del sistema antes de escribir cualquier test.

### Pregunta 16:

¿Cuál de las siguientes situaciones indicaría un 'code smell' en el contexto de TDD, relacionado con los tests?

    ⬜ Tests con código de setup muy largo y repetitivo.

    ⬜ Tests que se ejecutan muy rápido.

    ⬜ Tests que prueban una sola cosa a la vez.

    ⬜ Tests con nombres descriptivos y claros.

### Pregunta 17:

Si durante la fase 'Green' introduces duplicación de código para hacer pasar el test, ¿es esto aceptable en TDD?

    ⬜ No, nunca se debe introducir duplicación, es una violación fundamental de TDD.

    ⬜ Sí, es aceptable temporalmente, ya que la fase 'Refactor' se encargará de eliminarla.

    ⬜ Solo si la duplicación es mínima y no afecta el rendimiento.

### Pregunta 18:

¿Cómo influye TDD en el diseño de software?

    ⬜ Fuerza un diseño upfront exhaustivo antes de cualquier codificación.

    ⬜ Permite un diseño orgánico y emergente, guiado por la retroalimentación de los tests.

    ⬜ No tiene ningún impacto en el diseño, solo en la calidad del código.

    ⬜ Conduce inevitablemente a un diseño monolítico y acoplado.

### Pregunta 19:

Según el libro, si estás trabajando en pareja (pair programming) y el tiempo se acaba, ¿cómo deberías dejar los tests?

    ⬜ Dejar el último test fallando para recordar dónde continuar.

    ⬜ Asegurarse de que todos los tests estén pasando y el código esté limpio.

    ⬜ Borrar todos los tests temporales antes de terminar.

    ⬜ No importa el estado, siempre y cuando se haya avanzado en la funcionalidad.

### Pregunta 20:

Un 'Test Double' como un Mock Object es útil en TDD cuando:

    ⬜ Se necesita simular el comportamiento de dependencias externas (bases de datos, servicios, etc.) para aislar la unidad bajo prueba.

    ⬜ Se quiere acelerar el proceso de compilación del proyecto.

    ⬜ Se está probando la interfaz de usuario directamente.

    ⬜ El código de producción ya está terminado y se están añadiendo tests retrospectivamente.