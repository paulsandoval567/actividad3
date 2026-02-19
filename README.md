# actividad3
Estudiante Paul Ángel Sandoval Ortega


El trabajo se desarrolló siguiendo el enfoque de la Actividad 03 – Modelado UML de Requerimientos, aplicando refinamiento funcional y coherencia estructural entre diagramas.

1. Historia de Usuario Original

Como bibliotecario, quiero registrar el préstamo de un libro a un estudiante, para llevar control de los libros prestados y su fecha de devolución.

2. Análisis de la Historia Original

La historia inicial describe una funcionalidad básica: registrar préstamos.

Sin embargo, durante el análisis se identificaron múltiples ambigüedades:

No se especificaban validaciones previas.

No se establecían restricciones del estudiante.

No se definían estados del préstamo.

No se contemplaban escenarios alternativos.

No se incluían reglas sobre multas o límites.

No se consideraba la disponibilidad del libro.

Estas omisiones podían generar inconsistencias en el modelado UML y contradicciones entre diagramas.

3. Historia de Usuario Refinada

Como bibliotecario, quiero registrar y gestionar préstamos de libros a estudiantes, validando disponibilidad del libro, multas pendientes y límite de préstamos, para mantener control del estado del préstamo y garantizar la devolución oportuna.

4. Reglas de Negocio Definidas

Durante el refinamiento se establecieron reglas explícitas:

Un estudiante no puede tener más de 3 préstamos activos.

Un estudiante con multas pendientes no puede solicitar nuevos préstamos.

Un libro solo puede prestarse si está disponible.

Cada préstamo tiene una fecha de devolución.

Un préstamo puede renovarse una sola vez si no está vencido.

Si el libro se devuelve fuera de plazo, se genera una multa.

La multa queda registrada en el sistema.

Estados del préstamo:

Activo

Renovado

Vencido

Devuelto

Estados del libro:

Disponible

Prestado

Estas reglas permitieron estructurar formalmente el comportamiento del sistema.

5. Escenarios Identificados
5.1 Escenario Principal (Flujo Normal)

El bibliotecario ingresa datos del estudiante y libro.

El sistema valida multas pendientes.

El sistema valida límite de préstamos.

El sistema valida disponibilidad del libro.

Se registra el préstamo.

Se asigna fecha de devolución.

Se actualiza el estado del libro a “Prestado”.

5.2 Escenarios Alternativos

Estudiante con multas → Se rechaza el préstamo.

Límite de préstamos superado → Se rechaza el préstamo.

Libro no disponible → Se rechaza el préstamo.

Préstamo vencido → Cambia a estado “Vencido”.

Devolución fuera de plazo → Se genera multa.

6. Justificación del Refinamiento

El refinamiento fue necesario para:

Eliminar ambigüedades.

Definir reglas claras de negocio.

Asegurar coherencia entre diagramas.

Representar escenarios alternativos.

Modelar una situación realista.

Evitar contradicciones en UML.

Sin el refinamiento, los diagramas habrían sido incompletos o inconsistentes.

7. Impacto del Refinamiento en el Modelado UML

El refinamiento permitió estructurar correctamente los 5 diagramas solicitados:

🔹 Diagrama de Casos de Uso

Se incorporaron validaciones como casos extendidos (multas, límite, disponibilidad).

🔹 Diagrama de Actividades

Se añadieron nodos de decisión para representar validaciones y flujos alternativos.

🔹 Diagrama de Clases

Se definieron:

Atributos como fechaDevolucion, estado

Métodos como validarLimite(), calcularMulta()

Relaciones y cardinalidades coherentes

🔹 Diagrama de Secuencia

Se modelaron interacciones detalladas:

Validaciones previas

Cambios de estado

Generación de multa

🔹 Diagrama de Estados

Se definió el ciclo de vida formal del préstamo:

Activo → Renovado → Vencido → Devuelto

Esto garantizó coherencia estructural y funcional entre todos los modelos.
