# PI1 · Inspección del repositorio

**Primero, CA1–CA9.** Lee el dossier factual del aula virtual y sus límites antes de observar este snapshot. El dossier sigue siendo la fuente principal; el código aporta observaciones adicionales sobre una selección de un estado técnico.

Abre estos archivos en el navegador. No necesitas cuenta GitHub, Git, clonar, Java, SQL Server ni ejecutar nada. Basta con localizar las palabras indicadas: no se pide comprender la arquitectura ni cada línea.

**Carga orientativa: 20 minutos dentro de la actividad ClassAgenda existente:** 4 minutos para recordar el dossier, 10 para las cinco rutas y 6 para la salida individual. No añade otra entrega ni cambia la evaluación o el nivel de IA de PI1. Si te bloquea la sintaxis, conserva la pregunta y vuelve al dossier.

En la edición publicada debe consultarse la etiqueta estable `student-reference-2026-27` que indique el aula virtual. La mera mención de esa etiqueta en esta guía no acredita que ya esté creada.

## 1. El servidor

Ruta: [HttpServerBootstrap.java](../backend/src/main/java/com/classagendaprofessor/shared/http/HttpServerBootstrap.java).

- **QUÉ MIRAR:** `HttpServer.create`, la ruta `/health` y la llamada `ExampleRouter.registerRoutes`.
- **HECHO QUE PUEDE SOSTENER:** esta versión contiene código para crear un servidor HTTP y registrar una ruta de comprobación y rutas de ejemplo.
- **QUÉ NO PERMITE AFIRMAR:** que hubiera un servidor desplegado, personas utilizándolo o una agenda completa accesible.
- **PREGUNTA GUIADA:** ¿qué evidencia distinta del código necesitarías para afirmar que alguien utilizó el servicio?

## 2. Una tarea

Ruta: [Task.java](../backend/src/main/java/com/classagendaprofessor/features/task/domain/model/Task.java).

- **QUÉ MIRAR:** los nombres `title`, `status`, `priority`, `ownerId` y `validateIsOwnedBy`. No necesitas interpretar los tipos Java.
- **HECHO QUE PUEDE SOSTENER:** el modelo asocia una tarea con un propietario, un estado y una prioridad, y contiene una comprobación del identificador de propietario.
- **QUÉ NO PERMITE AFIRMAR:** que usuarios reales pidieran esas propiedades o que todas las peticiones de la aplicación ejecutaran la comprobación.
- **PREGUNTA GUIADA:** elige una propiedad: ¿qué preguntarías a una persona antes de decidir que la necesita?

## 3. Guardar y buscar

Ruta: [JdbcTaskRepository.java](../backend/src/main/java/com/classagendaprofessor/features/task/data/repository/JdbcTaskRepository.java).

- **QUÉ MIRAR:** los nombres `save`, `findByOwnerId` y `findByOwnerIdAndStatus`; observa que delegan operaciones en `taskDao`.
- **HECHO QUE PUEDE SOSTENER:** la selección contiene operaciones para guardar tareas y buscarlas por propietario o estado.
- **QUÉ NO PERMITE AFIRMAR:** que esas funciones se usaran, resolvieran una necesidad prioritaria o constituyeran una arquitectura que deba copiarse.
- **PREGUNTA GUIADA:** ¿buscar tareas por estado es una necesidad demostrada o una posible respuesta técnica? ¿Qué te falta saber?

## 4. Persistencia

Ruta: [TaskDao.java](../backend/src/main/java/com/classagendaprofessor/features/task/data/local/dao/TaskDao.java).

- **QUÉ MIRAR:** localiza `INSERT INTO TASKS`, `SELECT` y `prepareStatement`; no estudies todo el archivo ni ejecutes las consultas.
- **HECHO QUE PUEDE SOSTENER:** este código expresa operaciones SQL sobre tareas y recibe una conexión para realizarlas.
- **QUÉ NO PERMITE AFIRMAR:** que la base de datos estuviera disponible, contuviera datos reales o que esas operaciones funcionaran en un despliegue concreto.
- **PREGUNTA GUIADA:** ¿qué dependencia técnica observas y qué información pedirías para saber si llegó a condicionar el trabajo?

## 5. Una regla y sus pruebas

Ruta: [TaskTest.java](../backend/src/test/java/com/classagendaprofessor/features/task/domain/model/TaskTest.java).

- **QUÉ MIRAR:** los tres métodos marcados `@Test`: propietario diferente, propietario coincidente y estado inicial pendiente. Las cifras son identificadores de ejemplo.
- **HECHO QUE PUEDE SOSTENER:** hay tres pruebas escritas para esas reglas del modelo de tareas.
- **QUÉ NO PERMITE AFIRMAR:** que los tests hayan pasado, que cubran todo el producto, que la API sea segura o que se haya investigado a los usuarios.
- **PREGUNTA GUIADA:** ¿qué prueba sobre el comportamiento técnico ves y qué pregunta sobre el valor para una persona sigue sin responderse?

## Salida individual

Integra la observación en la reflexión de **100–150 palabras** del portfolio ClassAgenda ya prevista. Mantén sus preguntas y añade una ruta como evidencia: un **HECHO** visible, una **INFERENCIA** etiquetada y una **PREGUNTA ABIERTA** que el código no resuelve. No entregues código ni diseñes todavía funcionalidades de AulaFlow.

No atribuyas causas de éxito o fracaso al proyecto. Necesidad, demanda e investigación de usuarios requieren otras fuentes.
