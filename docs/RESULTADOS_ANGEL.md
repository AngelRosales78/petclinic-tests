# Resultados de Ángel Rosales

Validacion real del 3 de noviembre de 2026 con JDK 21.0.12, Maven Wrapper 3.9.11, Spring Boot 3.5.14 y H2 en memoria.

## Ejecuciones

1. `./mvnw.cmd test "-Dtest=VetSpecialtyServiceMockitoTest,VetSpecialtyServiceTest"`: BUILD SUCCESS; 31 pruebas, 0 fallos, 0 errores y 0 omitidas.
2. `./mvnw.cmd clean test`: BUILD SUCCESS; 58 pruebas, 0 fallos, 0 errores y 0 omitidas. Duracion informada por Maven: 59.453 segundos; finalizo a las 13:59:44, hora de Lima.

Se configuro JAVA_HOME para JDK 21 y LOGGING_FILE_NAME=logs/application.log para mantener los registros de la aplicacion dentro del repositorio. La primera descarga del wrapper no pudo escribir en la cache restringida; la ejecucion posterior con acceso a la cache y a las dependencias termino correctamente. No se cuentan intentos fallidos como pruebas aprobadas.

| Clase o bloque | Pruebas | Fallos | Errores | Omitidas |
|---|---:|---:|---:|---:|
| VetSpecialtyServiceMockitoTest de Ángel | 17 | 0 | 0 | 0 |
| VetSpecialtyServiceTest H2 de Ángel | 14 | 0 | 0 | 0 |
| TypeServiceMockitoTest de Diego | 8 | 0 | 0 | 0 |
| TypeServiceTest H2 de Diego | 4 | 0 | 0 | 0 |
| PetServiceMockitoTest original | 7 | 0 | 0 | 0 |
| PetServiceTest original | 7 | 0 | 0 | 0 |
| PetClinicApplicationTests original | 1 | 0 | 0 | 0 |
| Total | 58 | 0 | 0 | 0 |

Las 31 pruebas nuevas son de Ángel: los 12 escenarios requeridos estan cubiertos tanto con Mockito como con H2; se agregan cinco pruebas unitarias de validaciones y dos de restricciones reales de base de datos. Los informes XML de target/surefire-reports y la salida de Maven respaldan estos resultados. Mockito muestra una advertencia sobre carga dinamica de agentes en JDK 21; no produjo fallos.

Se verifico que schema.sql, data.sql y todos los archivos de implementacion y pruebas de Type conservan el contenido de feature/diego-caso-5.

## Revision del PR de Diego

Se reviso el diff del PR [#1](https://github.com/DiegoMagallanes11/petclinic-tests/pull/1), commit 1b205bb8b0965b844c83e55d3d439cfa0d024916. No se identificaron problemas que bloqueen el alcance del caso 5. La suite completa anterior incluye sus doce pruebas sin modificaciones. Tambien se consulto su ejecucion de GitHub Actions 41697499594, completada con conclusion success.

La aprobacion no pudo publicarse: el conector devolvio HTTP 403, Resource not accessible by integration. El intento alternativo mediante navegador se detuvo porque el control no pudo verificar la URL actual. La revision tecnica esta realizada, pero la aprobacion en GitHub queda pendiente y no debe presentarse como registrada.

## Pendientes del equipo

- Publicar desde la cuenta AngelRosales78 la aprobacion real del PR #1 de Diego, si sigue abierto.
- Diego debe revisar el PR de Ángel; integrar los PR corresponde al equipo despues de las revisiones.
- Al integrar el PR #1, cambiar a main la base del PR de Ángel si sigue apuntando a feature/diego-caso-5.
- No se produjo ningun conflicto durante este trabajo. Falta cumplir y documentar con evidencia real el conflicto exigido por TASKS.md.
- Obtener las capturas reales del historial de Git y las interacciones de GitHub, y completar el informe del laboratorio con tres conclusiones basadas en la ejecucion.

Estos resultados locales no afirman una ejecucion de CI de la rama de Ángel ni un merge que todavia no se hayan verificado.
