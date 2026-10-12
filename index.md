---
permalink: /
layout: default
title: Práctica 01 · Brazos robóticos
nav_order: 1
---

# Práctica 01 · Brazos robóticos

**Equipo Tortuga · Ingeniería Mecatrónica y Sistemas Ciberfísicos · IBERO**

Diseño, fabricación e integración de dos manipuladores de cuatro servomotores: **MeArm de piezas planas** y **EEZYbotARM impreso en 3D**. Una ESP32 administra ambos brazos mediante un PCA9685. Cada brazo tiene dos joysticks; un electrodo táctil habilita el modo remoto Wi-Fi.

![E01: sistema real con ambos brazos, cuatro joysticks y electrónica]({{ '/assets/img/practica01/sistema-completo.png' | relative_url }})

**E01.** Fotografía proporcionada del montaje: brazo de acrílico a la izquierda, brazo impreso a la derecha, cuatro joysticks y ESP32 sobre el tablero. La fotografía acredita presencia y montaje, pero no mide desempeño.

## Recorrido del reporte

1. [Concepto, objetivos y selección]({{ '/02-descripcion/' | relative_url }}).
2. [Arquitectura y diagramas]({{ '/03-diagramaBloques/' | relative_url }}).
3. [Fabricación 2D]({{ '/04-Robot2D/' | relative_url }}) y [fabricación 3D con visor]({{ '/05-Robot3D/' | relative_url }}).
4. [Electrónica y conexiones]({{ '/06-electronica/' | relative_url }}).
5. [Programación, interfaz y operación]({{ '/07-programacion/' | relative_url }}).
6. [Integración y pruebas]({{ '/08-pruebas/' | relative_url }}).
7. [Comparación y conclusiones]({{ '/09-conclusiones/' | relative_url }}).
8. [Matriz de los 31 criterios y entregables]({{ '/10-rubrica/' | relative_url }}).

> **Alcance de la evidencia:** se incluyen los archivos recibidos, las dos fotografías y el firmware recuperado. Las mediciones, parámetros de máquina, evidencia de soldadura y prueba funcional no proporcionados se señalan como pendientes. No se atribuye a la práctica una validación experimental que no esté documentada.

El [proyecto de tortuga suave]({{ '/12-proyecto-tortuga/' | relative_url }}) se conserva como trabajo independiente.
