---
permalink: /04-robot2d-proceso-ensamble/
layout: default
title: Proceso y ensamble final
nav_order: 4
parent: Robot 2D
---

# Proceso y ensamble final

## 9. Registro de fabricación

| Campo | Información disponible |
|---|---|
| Versión | V2D — MeArm |
| Proceso declarado | Corte láser de piezas planas |
| Archivo recibido | MeArm_piezas_P1_a_P36.pdf |
| Archivo editable / CAM usado | No proporcionado |
| Material | Acrílico declarado; grado y espesor sin registro |
| Máquina, potencia, velocidad, pasadas | No proporcionados |
| Compensación de kerf | Sin registro |
| Ajustes y fecha de fabricación | Sin registro |
| Evidencia | E01, conjunto terminado |

## 10. Secuencia de construcción

![Secuencia propuesta de ensamblaje]({{ '/assets/diagrams/ensamble.svg' | relative_url }})

1. Revisar escala, espesor, ranuras y perforaciones antes del corte; realizar una probeta de ajuste.
2. Desbarbar sin modificar cotas funcionales y separar piezas por función.
3. Montar base y soportes; centrar cada servo desacoplado antes de colocar el horn.
4. Armar hombro, codo y paralelogramo; apretar únicamente hasta conservar giro libre.
5. Instalar pinza, fijar cables con holgura y sujetar la base al tablero.
6. Probar un eje a la vez, ajustar sentidos/límites y registrar interferencias.

Esta guía describe el orden técnico recomendado. No reemplaza una bitácora contemporánea de fabricación. Faltan fotografías de corte, piezas antes de montar y uniones intermedias.

## 12. Pruebas mecánicas

[Protocolo de movilidad, holgura, agarre y repetibilidad]({{ '/08-pruebas/' | relative_url }}). Registrar los resultados reales en `registros/pruebas.csv`; no hay mediciones adjuntas de esta versión.
