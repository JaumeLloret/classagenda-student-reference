# ClassAgenda · referencia histórica y didáctica

ClassAgenda fue un proyecto docente anterior. Este repositorio contiene un snapshot saneado de una selección de su código para observar decisiones técnicas en PI1 de 1.º DAM. No conserva el historial Git del proyecto original.

Snapshot didáctico derivado del estado técnico correspondiente al commit `80c087a661db8fef1bd52bcd895cfed46da33dc0` de un repositorio docente privado. La [procedencia](PROVENANCE.md) explica la selección y sus límites.

## Cómo utilizarlo en PI1

Primero lee el dossier **CA1–CA9** del aula virtual: sigue siendo la fuente principal del caso. Después abre la [guía de inspección](docs/PI1_INSPECTION.md), con cinco rutas y preguntas para distinguir **HECHO / INFERENCIA / PREGUNTA ABIERTA**. Esta observación complementa la actividad existente y su salida individual.

Solo necesitas un navegador. **No necesitas ejecutar el proyecto, instalar SQL Server ni Java, clonar, utilizar Git o tener una cuenta GitHub.** No es necesario comprender cada instrucción del código.

## Qué permite observar

En los archivos seleccionados aparecen un servidor HTTP, un modelo de tareas con propietario y estado, operaciones de persistencia y pruebas de algunas reglas. Son decisiones plasmadas en una versión concreta.

El código **no demuestra investigación de usuarios, necesidad o demanda, ni éxito o fracaso**. Tampoco permite deducir qué llegó a desplegarse o utilizarse. La ausencia de una función en esta selección no demuestra que no existiera en otros momentos o materiales del curso anterior.

Este snapshot **no es una arquitectura recomendada para AulaFlow y no debe copiarse como plantilla**. PI1 utiliza el caso para formular preguntas antes de proponer soluciones; no para impartir arquitectura ni adelantar Git.

## Contexto técnico observable

- El `pom.xml` declara Java 21, Maven, JUnit y el controlador JDBC de SQL Server.
- El código utiliza `HttpServer` y JDBC. No se incluyen la base de datos, sus datos ni configuración de conexión.
- Se conservan cuatro clases de tests que no necesitan base de datos. Su presencia no acredita por sí sola que hayan pasado ni que el sistema completo funcione.
- El ejemplo de CI está adaptado para activación manual. Su existencia no acredita una ejecución de CI.

La selección conserva las fuentes de producción y los archivos Maven para permitir comprobaciones técnicas por parte del mantenimiento. No se entrega un despliegue completo: faltan deliberadamente infraestructura, esquema y configuración de base de datos. **Ejecutar o compilar no forma parte del encargo PI1.**

## Procedencia y licencia

Consulta [PROVENANCE.md](PROVENANCE.md) y [LICENSE](LICENSE). Los scripts Maven conservan sus avisos originales de Apache. No se importan commits, autores, correos, ramas, etiquetas, PR ni objetos Git del proyecto anterior.

