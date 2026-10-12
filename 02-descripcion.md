---
permalink: /02-descripcion/
layout: default
title: Concepto y definición
nav_order: 3
---

# Concepto y definición

## 1. Problema, objetivos y requisitos

Se requiere comparar dos técnicas de fabricación mediante manipuladores capaces de orientar una base, posicionar una pinza y abrir o cerrar el efector. La operación debe ser intuitiva, independiente para cada brazo y reproducible con una sola unidad de procesamiento.

**Objetivo general.** Integrar un MeArm fabricado con piezas planas y un EEZYbotARM impreso, ambos de cuatro servos, bajo una ESP32, y documentar su construcción, control y evaluación con criterios comunes.

**Objetivos específicos.** Identificar piezas y uniones; implementar ocho canales de actuación; asignar dos joysticks a cada brazo; alternar entre manual y remoto; establecer límites por articulación; comparar montaje, movilidad y desempeño con evidencia trazable.

| ID | Requisito | Criterio de comprobación |
|---|---|---|
| R01 | Dos versiones físicas | Foto identificada de MeArm y EEZYbotARM |
| R02 | Cuatro servos por brazo | Base, codo, hombro y pinza; canales 0–7 |
| R03 | Dos joysticks por brazo | J1 X: base; J1 Y: codo; J2 Y: hombro; J2 X: pinza |
| R04 | Una ESP32 y PCA9685 | Conexiones I²C y PWM verificadas |
| R05 | Modo manual independiente | Cada eje actúa sobre su canal sin mover el otro brazo |
| R06 | Modo remoto | Cambio por touch, conexión al AP y respuesta a botones |
| R07 | Movimiento acotado | Centro estable, sentidos correctos y límites sin colisión |
| R08 | Entrega reproducible | Código, geometría, conexiones, instrucciones y registro de pruebas |

**Restricciones.** El firmware recuperado requiere ESP32 clásica WROOM-32 (no C3/C6/S3), servos posicionales, fuente externa para potencia y tierra común. Los límites iniciales 60–120° y posición 90° son consignas de prueba, pendientes de calibración mecánica. No existe sensor externo de posición ni control cartesiano implementado. La pinza añade una acción de apertura a los tres movimientos de posicionamiento; cuatro servos no equivalen a cuatro ejes independientes de pose cartesiana.

## 2. Bocetos de la solución

![Boceto funcional y secuencia mecánica]({{ '/assets/diagrams/ensamble.svg' | relative_url }})

El conjunto se organiza desde la base fija hacia la pinza: base giratoria, soportes de hombro, eslabones y paralelogramo, soporte de pinza y dedos. La transmisión mediante eslabones hace que las consignas de servo no se interpreten directamente como ángulos cartesianos del efector.

![Referencia de diseño incluida en el paquete EEZYbotARM]({{ '/assets/img/eezybotarm/EZYbotARM_01.png' | relative_url }})

Referencia del autor del modelo, **no fotografía del prototipo del equipo**. Véanse también las fotografías E01 y E02 y las láminas por pieza.

## 3. Alternativas y selección

| Decisión | Alternativas | Selección y justificación |
|---|---|---|
| Estructura | Placas cortadas / sólidos impresos | Se construyen ambas para comparar fabricación y ensamble; no se asume cuál es más resistente sin ensayo |
| Generación PWM | ESP32 directa / PCA9685 | PCA9685 concentra ocho salidas y mantiene pulsos mediante hardware; coincide con el firmware recuperado |
| Interfaz | Joysticks / navegador | Se conservan ambas: manual para control local; AP para acceso remoto sin router |
| Procesamiento | Dos ESP32 / una ESP32 | Una ESP32 comparte lógica, alimentación de control y comunicación; mantiene asignación independiente por canal |
| Regulación | Lazo abierto de consignas / sensores externos | Se usa el lazo externo abierto existente; la realimentación interna del servo no proporciona posición al ESP32 |

## 4. Arquitectura general

[Consultar el diagrama de subsistemas y el esquema electrónico]({{ '/03-diagramaBloques/' | relative_url }}). La selección prioriza compatibilidad con el montaje y el código existentes. Las ventajas dimensionales y de desempeño se deben comprobar con el protocolo común de pruebas.
