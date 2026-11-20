# Mis Ventas

*Ventas simples, control total.* App Android de punto de venta offline-first para Max Carlotas.
Desarrollado por **Ambulant Point** — Gestión de Proyectos de Software, ITZ, ago–dic 2026.

| Documento | Contenido |
|---|---|
| [docs/00-PLAN-MVP.md](docs/00-PLAN-MVP.md) | Plan de trabajo, alcance del MVP y fases |
| [docs/02-TRAZABILIDAD-DFR.md](docs/02-TRAZABILIDAD-DFR.md) | Estado de cada requerimiento funcional |
| [docs/03-GUION-DEMO.md](docs/03-GUION-DEMO.md) | Guion de la exposición de avance |
| [docs/04-ARQUITECTURA-APP.md](docs/04-ARQUITECTURA-APP.md) | Capas del código, decisiones de diseño y qué viene del DFR |
| [docs/05-VERIFICACION-DFR.md](docs/05-VERIFICACION-DFR.md) | Verificación del MVP contra el DFR: mensajes, reglas, desviaciones y pendientes |
| `docs/dfr/` | DFR v1.2 (fuente de verdad). **No se publica** porque contiene datos personales; está en la carpeta del proyecto de la materia |

Stack: Kotlin · Jetpack Compose · Material 3 · MVVM · Room · Firebase · Android 8.0+.

## Compilar

`./gradlew test assembleDebug`, con `JAVA_HOME` según el sistema:
- Windows: `JAVA_HOME="C:\Program Files\Android\Android Studio\jbr"`
- Linux: `JAVA_HOME=/usr/lib/jvm/java-21-openjdk` (o el `jbr` de Android Studio)

Archivos propios de cada equipo que no se suben: `local.properties` (ruta del SDK), `app/google-services.json`
(proyecto Firebase) y, para la versión de liberación, `keystore.properties` + `firma/` (`./gradlew assembleRelease`).

Pruebas en el teléfono: **siempre** con `-Pandroid.injected.androidTest.leaveApksInstalledAfterRun=true`.
Sin esa opción, `connectedDebugAndroidTest` desinstala la app al terminar y **borra todos sus datos**.

Datos de demo: `./gradlew connectedDebugAndroidTest -Pandroid.injected.androidTest.leaveApksInstalledAfterRun=true
-Pandroid.testInstrumentationRunnerArguments.class=mx.ambulantpoint.misventas.demo.CargarDatosDemo
-Pandroid.testInstrumentationRunnerArguments.demo=1` (ver `app/src/androidTest/.../demo/`).
