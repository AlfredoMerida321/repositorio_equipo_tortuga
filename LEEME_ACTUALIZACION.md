---
layout: default
title: Desarrollo de la práctica
nav_order: 12
permalink: /LEEME_ACTUALIZACION/
---

# Desarrollo de la práctica 01

## Sistema de brazos robóticos

La práctica integra dos manipuladores: un MeArm de piezas planas y un EEZYbotARM de piezas impresas. Cada brazo dispone de cuatro servomotores para base, codo, hombro y pinza. Una ESP32 clásica administra las entradas de cuatro joysticks y envía las consignas al controlador PCA9685.

## Objetivo de la práctica

Relacionar diseño mecánico, fabricación, electrónica y programación mediante dos versiones físicas con una misma interfaz de control. Comparar su montaje y movilidad bajo condiciones equivalentes y documentar los ajustes de cada mecanismo.

## Organización del sistema

- **Mecánica:** base, eslabones, uniones, soportes y pinza.
- **Entradas:** dos joysticks por brazo y un electrodo táctil para cambiar de modo.
- **Procesamiento:** ESP32 WROOM-32 con calibración de centros, filtro, zona muerta y límites por articulación.
- **Actuación:** PCA9685 con ocho canales PWM y alimentación externa para los servos.
- **Interfaz:** control manual local o control remoto desde un navegador conectado al punto de acceso del ESP32.

## Secuencia de trabajo

1. Identificar piezas y montar la estructura de cada versión.
2. Centrar los servos desacoplados, colocar los horns y comprobar las articulaciones.
3. Conectar alimentación, joysticks, ESP32 y PCA9685 conforme al pinout.
4. Cargar el firmware y calibrar sentidos, límites y posición inicial de cada eje.
5. Comprobar el control individual y los cambios entre manual y remoto.
6. Ejecutar ciclos de agarre, traslado y liberación; registrar resultados de ambas versiones.

## Recursos de la práctica

[Geometría y visor](05-Robot3D.md) · [Electrónica y pinout](06-electronica.md) · [Código e interfaz](07-programacion.md) · [Integración y ensayos](08-pruebas.md).

## Autoría de recursos

El diseño EEZYbotARM pertenece a daGHIZmo y conserva su licencia Creative Commons Attribution–NonCommercial. La documentación del equipo identifica las fotografías del montaje, los diagramas técnicos y los archivos asociados a cada subsistema.
