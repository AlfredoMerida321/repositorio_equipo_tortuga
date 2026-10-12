---
permalink: /03-diagramaBloques/
layout: default
title: Arquitectura y diagramas
nav_order: 4
---

# Arquitectura y diagramas

## Relación entre subsistemas

![Arquitectura general del sistema]({{ '/assets/diagrams/arquitectura.svg' | relative_url }})

Las flechas de los joysticks representan señales analógicas; la conexión ESP32–PCA9685 es I²C y las salidas a servos son PWM. La alimentación de potencia se distribuye por V+ y comparte referencia GND con la lógica. El cambio de modo proviene de GPIO4, no de los botones SW de los joysticks.

## Secuencia principal del software

![Diagrama de flujo del firmware]({{ '/assets/diagrams/flujo.svg' | relative_url }})

Ante fallo inicial del PCA9685 o centros ADC inválidos el programa se detiene y reporta por serie. En remoto, la caducidad de 450 ms detiene la actualización de consigna; no corta la energía ni elimina el par del servo.

## Esquemático modular editable

![Esquemático de conexiones con nombres de red]({{ '/assets/diagrams/esquematico.svg' | relative_url }})

Los diagramas están disponibles como SVG editables en `assets/diagrams/`. [Conexiones y verificaciones eléctricas]({{ '/06-electronica/' | relative_url }}).
