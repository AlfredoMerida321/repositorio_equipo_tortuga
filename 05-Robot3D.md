---
permalink: /05-Robot3D/
layout: default
title: Robot 3D y visor
nav_order: 6
---

# Robot 3D y visor

## Modelo, mecanismo y evidencia

EEZYbotARM, diseño de **daGHIZmo**, versión de archivos recibida con actualizaciones R01. El conjunto impreso utiliza base giratoria, eslabones, paralelogramo y pinza con engranes. Se conserva el archivo de licencia original **Creative Commons Attribution–NonCommercial**; las condiciones del autor prevalecen sobre el pie de página general del sitio para estos recursos.

![E02: EEZYbotARM real ensamblado]({{ '/assets/img/practica01/brazo-impreso.png' | relative_url }})

**E02.** Ensamble real proporcionado. Permite identificar base fija, soporte giratorio, eslabones, articulaciones y pinza. El polímero exacto y los parámetros de impresión no se pueden determinar con la fotografía.

## Visor 3D de las piezas originales

<iframe title="Visor interactivo de STL EEZYbotARM" class="model-viewer" src="{{ '/viewer.html' | relative_url }}" width="100%" height="620" allowfullscreen></iframe>

[Ampliar visor]({{ '/viewer.html' | relative_url }})

Arrastrar para rotar, rueda para acercar, seleccionar una pieza para inspeccionarla. Los botones permiten vistas isométrica, frontal, lateral y superior, y descarga del STL. **Despiece** muestra los archivos distribuidos en una cuadrícula, no un ensamble cinemático. No se entregaron transformaciones de montaje ni un CAD de conjunto; el visor no inventa esa geometría. Las dimensiones son envolventes del archivo, no recorridos del robot.

## 5–8. Inventario geométrico y láminas

Los STL contienen geometría triangulada, no un historial CAD paramétrico. Se incluyen 17 archivos originales, manifest de dimensiones y láminas SVG de referencia. Las unidades STL no están codificadas; se interpretan como mm y deben contrastarse con un componente real. Un archivo disponible no implica que se deba fabricar exactamente una unidad: revisar multiplicidad en el ensamble. El soporte Maestro pertenece al diseño de referencia y no se requiere para el controlador ESP32/PCA9685 descrito.

| Archivo / lámina | X | Y | Z | STL |
|---|---:|---:|---:|---|
| [EBA_01.00.001]({{ '/assets/plans/EBA_01.00.001.svg' | relative_url }}) | 52.00 | 61.10 | 52.63 | [Descargar]({{ '/assets/models/EBA_01.00.001.STL' | relative_url }}) |
| [EBA_01.00.002_vertical_drive_arm]({{ '/assets/plans/EBA_01.00.002_vertical_drive_arm.svg' | relative_url }}) | 46.49 | 12.99 | 7.50 | [Descargar]({{ '/assets/models/EBA_01.00.002_vertical_drive_arm.STL' | relative_url }}) |
| [EBA_01.00.003_link]({{ '/assets/plans/EBA_01.00.003_link.svg' | relative_url }}) | 92.00 | 12.00 | 5.00 | [Descargar]({{ '/assets/models/EBA_01.00.003_link.STL' | relative_url }}) |
| [EBA_01.00.004_forward_drive_arm]({{ '/assets/plans/EBA_01.00.004_forward_drive_arm.svg' | relative_url }}) | 92.46 | 29.00 | 15.00 | [Descargar]({{ '/assets/models/EBA_01.00.004_forward_drive_arm.STL' | relative_url }}) |
| [EBA_01.00.005_horizontal_arm]({{ '/assets/plans/EBA_01.00.005_horizontal_arm.svg' | relative_url }}) | 127.50 | 15.00 | 8.00 | [Descargar]({{ '/assets/models/EBA_01.00.005_horizontal_arm.STL' | relative_url }}) |
| [EBA_01.00.006_triangular_link]({{ '/assets/plans/EBA_01.00.006_triangular_link.svg' | relative_url }}) | 9.00 | 58.25 | 29.23 | [Descargar]({{ '/assets/models/EBA_01.00.006_triangular_link.STL' | relative_url }}) |
| [EBA_01.00.009_servo_plate]({{ '/assets/plans/EBA_01.00.009_servo_plate.svg' | relative_url }}) | 34.00 | 26.00 | 2.50 | [Descargar]({{ '/assets/models/EBA_01.00.009_servo_plate.STL' | relative_url }}) |
| [EBA_01.00.010_basement]({{ '/assets/plans/EBA_01.00.010_basement.svg' | relative_url }}) | 94.67 | 87.46 | 31.00 | [Descargar]({{ '/assets/models/EBA_01.00.010_basement.STL' | relative_url }}) |
| [EBA_01.00.011_round_plate]({{ '/assets/plans/EBA_01.00.011_round_plate.svg' | relative_url }}) | 72.00 | 72.00 | 8.50 | [Descargar]({{ '/assets/models/EBA_01.00.011_round_plate.STL' | relative_url }}) |
| [EBA_01.00.012_R01_claw_support]({{ '/assets/plans/EBA_01.00.012_R01_claw_support.svg' | relative_url }}) | 54.00 | 25.00 | 38.23 | [Descargar]({{ '/assets/models/EBA_01.00.012_R01_claw_support.STL' | relative_url }}) |
| [EBA_01.00.013_R01_right_finger]({{ '/assets/plans/EBA_01.00.013_R01_right_finger.svg' | relative_url }}) | 58.42 | 14.02 | 9.00 | [Descargar]({{ '/assets/models/EBA_01.00.013_R01_right_finger.STL' | relative_url }}) |
| [EBA_01.00.014_R01_left_finger]({{ '/assets/plans/EBA_01.00.014_R01_left_finger.svg' | relative_url }}) | 58.42 | 14.50 | 9.00 | [Descargar]({{ '/assets/models/EBA_01.00.014_R01_left_finger.STL' | relative_url }}) |
| [EBA_01.00.015_drive_gear]({{ '/assets/plans/EBA_01.00.015_drive_gear.svg' | relative_url }}) | 20.00 | 20.00 | 5.00 | [Descargar]({{ '/assets/models/EBA_01.00.015_drive_gear.STL' | relative_url }}) |
| [EBA_01.00.016_R01_driven_gear]({{ '/assets/plans/EBA_01.00.016_R01_driven_gear.svg' | relative_url }}) | 28.00 | 21.47 | 7.00 | [Descargar]({{ '/assets/models/EBA_01.00.016_R01_driven_gear.STL' | relative_url }}) |
| [EBA_01.00.017_R01_ramp]({{ '/assets/plans/EBA_01.00.017_R01_ramp.svg' | relative_url }}) | 131.00 | 114.44 | 112.29 | [Descargar]({{ '/assets/models/EBA_01.00.017_R01_ramp.STL' | relative_url }}) |
| [EBA_01.00.018_maestro_holder]({{ '/assets/plans/EBA_01.00.018_maestro_holder.svg' | relative_url }}) | 33.00 | 21.00 | 50.00 | [Descargar]({{ '/assets/models/EBA_01.00.018_maestro_holder.STL' | relative_url }}) |
| [EBA_01.00.019_ball]({{ '/assets/plans/EBA_01.00.019_ball.svg' | relative_url }}) | 11.99 | 12.00 | 11.98 | [Descargar]({{ '/assets/models/EBA_01.00.019_ball.STL' | relative_url }}) |


Las láminas contienen proyecciones ortogonales y cotas envolventes. **No sustituyen planos de fabricación completos**: faltan cotas de taladros, tolerancias, ajustes y material confirmado. El STL puede usarse en un laminador tras comprobar escala e integridad.

## 6. Materiales mecánicos de la versión impresa

| Elemento | Cantidad | Especificación disponible |
|---|---|---|
| Juego estructural EEZYbotARM | Un brazo; 17 STL disponibles | Polímero sin ficha de material; contabilizar instancias necesarias |
| Servos posicionales | 4 | Se ve microservo SG90 en pinza; inventario de los demás pendiente |
| Tornillos, tuercas y ejes | Según ensamble | Medir diámetros y longitudes antes de adquirir |
| Base común | Compartida | Tablero observado en E01/E02 |

## 9. Registro de impresión

| Campo | Estado |
|---|---|
| Versión | V3D — EEZYbotARM |
| Proceso | Impresión 3D; piezas ensambladas visibles |
| Material, impresora y boquilla | Sin registro proporcionado |
| Altura de capa, perímetros y relleno | Sin registro proporcionado |
| Temperatura, velocidad, soportes y orientación | Sin registro proporcionado |
| Archivos | STL originales incluidos; proyecto de laminado/G-code no recibido |
| Ajustes físicos | Sin bitácora proporcionada |

No se proponen parámetros como si hubieran sido los usados. Completar `registros/fabricacion.csv` con la configuración del laminador y evidencia de máquina.

## 10–12. Montaje y comprobación

![Orden técnico de montaje]({{ '/assets/diagrams/ensamble.svg' | relative_url }})

Comprobar giro de base, ejes libres, paralelismo, engrane de dedos y recorrido de cables antes de energizar. Después calibrar cada servo sin carga. Las fotos acreditan el ensamblaje terminado; los ensayos y resultados están [definidos para registro]({{ '/08-pruebas/' | relative_url }}), todavía sin mediciones.

## Archivos de origen

[Descripción original]({{ '/assets/models/README.txt' | relative_url }}) · [Licencia original]({{ '/assets/models/LICENSE.txt' | relative_url }}) · [Dimensiones CSV]({{ '/assets/files/dimensiones-stl.csv' | relative_url }})
