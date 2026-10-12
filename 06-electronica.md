---
permalink: /06-electronica/
layout: default
title: Electrónica y conexiones
nav_order: 7
---

# Electrónica y conexiones

## 13. Diagrama de bloques electrónico

![Esquemático modular]({{ '/assets/diagrams/esquematico.png' | relative_url }})

[Descargar SVG editable]({{ '/assets/diagrams/esquematico.svg' | relative_url }}). El esquema expresa las conexiones del firmware de la práctica. Las etiquetas de red iguales indican continuidad eléctrica. Corresponde a módulos comerciales, no al circuito interno de la ESP32 ni del PCA9685. El cableado exacto del montaje debe verificarse por continuidad; no puede reconstruirse completamente a partir de las fotos.

## 14. Lista de materiales electrónicos

| Ref. | Componente | Cantidad | Función / adquisición |
|---|---|---:|---|
| U1 | ESP32 clásica WROOM-32, Dev Module | 1 | ADC, touch y Wi-Fi; proveedor del montaje no registrado |
| U2 | Módulo PCA9685, dirección 0x40 | 1 | Ocho salidas PWM a 50 Hz; referencia del firmware |
| J1–J4 | Joystick analógico de dos ejes | 4 | Alimentar a 3.3 V; SW sin uso |
| M1–M8 | Servos posicionales | 8 | Cuatro por brazo; números de parte por eje pendientes |
| E1 | Electrodo capacitivo | 1 | Placa conductora y cable corto a GPIO4/T0; ubicación no identificable en fotos |
| PS1 | Fuente externa regulada para servos | 1 | Tensión según ficha de todos los servos; corriente a dimensionar y medir |
| U3 | Convertidor DC/DC visible en E01 | 1 observado | Modelo, ajuste y conexión exacta sin confirmar |
| PCB1 | Adaptador ESP32 con borneras | 1 observado | Conexión mecánica/eléctrica, diseño comercial sin archivos |
| USB | Cable de alimentación/programación | 1 | ESP32; no utilizar para alimentar los ocho servos |
| CN | Cables, conectores y distribución | Lote | Cantidades, calibre y terminales pendientes de inventario |

No se atribuyen precios o proveedores no documentados. El dimensionamiento de fuente requiere sumar corrientes de los servos en la condición de operación y prever picos simultáneos, después contrastar caída de tensión y calentamiento. No se puede calcular una corriente nominal fiable sin conocer los modelos exactos.

## 15. Conexiones completas de control

**Brazo 1 = MeArm; brazo 2 = EEZYbotARM.** Esta convención debe coincidir con el cableado físico antes de ejecutar el programa.

| Brazo | Joystick / eje | GPIO ADC | Acción | PCA9685 |
|---|---|---:|---|---|
| 1 | J1 VRx | 32 | Base izquierda/derecha | CH0 |
| 1 | J1 VRy | 33 | Codo adelante/atrás | CH1 |
| 1 | J2 VRy | 34 | Hombro adelante/atrás | CH2 |
| 1 | J2 VRx | 35 | Pinza abrir/cerrar | CH3 |
| 2 | J3 VRx | 36 / VP | Base izquierda/derecha | CH4 |
| 2 | J3 VRy | 39 / VN | Codo adelante/atrás | CH5 |
| 2 | J4 VRy | 25 | Hombro adelante/atrás | CH6 |
| 2 | J4 VRx | 26 | Pinza abrir/cerrar | CH7 |

| Origen | Destino | Red / función |
|---|---|---|
| ESP32 3V3 | VCC de PCA9685 y de J1–J4 | Alimentación lógica y analógica |
| ESP32 GPIO21 | SDA PCA9685 | I²C datos |
| ESP32 GPIO22 | SCL PCA9685 | I²C reloj |
| ESP32 GPIO4 | E1 | Electrodo touch; no unir a VCC/GND |
| Fuente externa positiva | PCA9685 V+ | Potencia servos, tensión nominal según modelos |
| Fuente negativa, ESP32 GND, PCA GND, J1–J4 GND | Entre sí | Referencia común |
| PCA9685 OE | GND | Salidas habilitadas; no hay corte de potencia por software |
| PCA9685 A0–A5 | Abiertos | Dirección I²C 0x40 |
| Cada CH0–CH7 | Señal del servo correspondiente | Cable S; V+ y GND a pines de potencia correctos |

GPIO25 y GPIO26 utilizan ADC2 en la ESP32 clásica, compartido con Wi-Fi. El firmware evita su lectura en remoto y apaga Wi-Fi para control manual. [Referencia Espressif](https://docs.espressif.com/projects/esp-idf/en/v4.2/esp32/api-reference/peripherals/adc.html).

## 16–17. Tarjeta, montaje y manufactura

E01 muestra un adaptador con borneras y un montaje modular. **No se recibieron archivos de una PCB propia, Gerbers, perforaciones, ni fotos de su fabricación/soldadura.** El esquemático modular y la tabla son editables y reproducibles, pero no acreditan una tarjeta diseñada y fabricada por el equipo. Este criterio permanece pendiente si la práctica exige PCB propia.

Para cerrarlo: anexar el esquemático y PCB nativos de la tarjeta realmente utilizada, dimensiones y conectores, capas de cobre/serigrafía, archivos de fabricación y fotos de ambas caras antes/después de soldar. Si se utilizó placa perforada, documentar esa técnica, distribución y puentes reales sin presentarla como PCB grabada.

La foto E01 documenta ubicación general de los controles y cableado. Las correcciones de soldadura y continuidad no tienen registro adjunto.

## 18. Pruebas por bloques

| Prueba | Procedimiento antes de integrar | Resultado requerido |
|---|---|---|
| Alimentación | Medir 3V3 y V+ sin carga y con un servo | Tensiones registradas y dentro de ficha técnica |
| Continuidad | Equipo sin energía: verificar GND y ausencia de corto V+/GND | Valor/observación y foto del punto |
| I²C | Verificar respuesta del PCA9685 en arranque | No aparece error “PCA9685 no encontrado” |
| Entradas | Centrar joysticks al arrancar; variar cada eje en manual | Centro válido y canal correcto |
| PWM | Osciloscopio en CH0–CH7, frecuencia 50 Hz | Periodo cercano a 20 ms y pulso consistente con consigna |
| Touch | Toque sostenido y liberación | Un cambio de modo por toque |

**Estado:** protocolos definidos; faltan mediciones fechadas y capturas de instrumentos. Registrar resultados en `registros/pruebas.csv`.


## Pinout gráfico y descargas

![Pinout completo]({{ '/assets/diagrams/pinout.png' | relative_url }})

[Pinout editable SVG]({{ '/assets/diagrams/pinout.svg' | relative_url }}) · [Pinout PNG]({{ '/assets/diagrams/pinout.png' | relative_url }}) · [Tabla CSV]({{ '/assets/files/Pinout_Brazos.csv' | relative_url }}) · [Código y conexiones ZIP]({{ '/assets/files/Brazos_Gemelos.zip' | relative_url }}).
