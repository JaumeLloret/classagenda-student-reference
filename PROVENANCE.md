# Procedencia del snapshot didáctico

```yaml
source_repository: PRIVATE HISTORICAL TEACHING REPOSITORY
source_commit: 80c087a661db8fef1bd52bcd895cfed46da33dc0
snapshot_policy: ALLOWLIST_ONLY
history_imported: false
```

Snapshot didáctico derivado del estado técnico correspondiente al commit indicado de un repositorio docente privado. La denominación de la fuente identifica su procedencia prevista; no es una certificación de la configuración de acceso actual del repositorio original.

Se han revisado individualmente los archivos seleccionados en esa versión exacta y se han contrastado sus bytes con sus objetos de origen. No se importa historia Git, refs, PR, incidencias, autores ni correos de commits históricos. El repositorio nuevo debe comenzar con historia independiente.

La selección conserva fuentes Java, configuración Maven, scripts de Maven Wrapper, cuatro clases de tests sin base de datos y licencia. El workflow de CI, inicialmente manual, se adapta en 1G-quater a un único intento por `push` en `work/student-reference-2026-27`, con permisos de lectura, checkout del SHA del evento, Java 21 e informes privados; conserva la activación manual para uso posterior en esa misma referencia. Esta excepción autorizada respecto al baseline `6c28de48d27d25d02930c17a29aa4edef8619945` afecta solo a `.github/workflows/ci.yml` y a su descripción en README y PROVENANCE; los otros 38 archivos conservan bytes y modos. No implica publicación ni acredita por sí sola una ejecución correcta. El README, esta procedencia, la guía PI1 y las reglas de exclusión son documentos nuevos.

Se excluyen configuración de conexión, infraestructura y datos de base de datos, archivos del IDE, resultados de compilación, binarios, informes, logs y pruebas que requieran infraestructura o contengan identidades de prueba no verificadas. No se enumeran valores de contenidos excluidos por seguridad o privacidad.

La ausencia de archivos se debe a la política de selección; no permite reconstruir todo el proyecto anterior ni juzgar sus resultados. El snapshot está pensado solo para inspección docente mediante navegador, con el dossier CA1–CA9 como fuente principal. No acredita investigación de usuarios ni calidad de una arquitectura.

