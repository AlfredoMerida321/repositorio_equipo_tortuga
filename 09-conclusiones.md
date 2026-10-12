---
permalink: /09-conclusiones/
layout: default
title: Comparación y conclusiones
nav_order: 10
---

# Comparación y conclusiones

## 29. Comparación de versiones

| Criterio común | V2D — MeArm | V3D — EEZYbotARM |
|---|---|---|
| Arquitectura | Eslabones planos con uniones atornilladas | Eslabones impresos y soportes volumétricos |
| Proceso documentado | Corte láser declarado; sin parámetros | Impresión 3D; sin parámetros |
| Archivo disponible | PDF con P1–P36 | 17 STL y referencias gráficas del autor |
| Evidencia de ensamble | E01 | E01 y E02 |
| Control | CH0–CH3, dos joysticks | CH4–CH7, dos joysticks |
| Plataforma electrónica | ESP32 + PCA9685 compartidos | ESP32 + PCA9685 compartidos |
| Masa, tamaño final, costo | Pendiente de medir/inventariar | Pendiente de medir/inventariar |
| Tiempo de fabricación y ensamble | Sin registro | Sin registro |
| Holgura, carga y repetibilidad | Ensayos T10–T13 pendientes | Ensayos T10–T13 pendientes |
| Ciclos y modos demostrados | Sin evidencia funcional validada | Sin evidencia funcional validada |

La comparación cuantitativa se debe realizar con el mismo protocolo. No se concluye superioridad de rigidez, velocidad o precisión a partir de la apariencia.

## 30. Conclusiones técnicas

Las fotografías permiten concluir que ambas arquitecturas llegaron a un ensamblaje físico y comparten una estación de control. El código recuperado permite asignar ocho canales de servo a ocho ejes de joystick y ofrece una interfaz remota mediante AP. La separación manual/remoto es consistente con el uso de ADC2 en GPIO25/26.

La documentación entregada ahora relaciona arquitectura, conexiones, funciones, geometría y procedimiento de operación. La geometría STL permite inspección tridimensional por pieza y preparación de impresión tras validar escala; no reemplaza un ensamble CAD ni planos con tolerancias.

Persisten limitaciones para afirmar cumplimiento experimental: faltan registros de fabricación, versiones de dependencias, archivos de tarjeta propia y resultados de ensayos. La detención remota mantiene el servo energizado y la posición reportada por software es una consigna. No hay evidencia suficiente para afirmar precisión, carga útil o fiabilidad.

Las principales correcciones documentales fueron retirar texto de plantilla, separar la tortuga suave de esta práctica, reemplazar enlaces a imágenes inexistentes por fotografías reales, incorporar el firmware previo y distinguir evidencia de planes de prueba. La siguiente etapa técnica es calibrar cada articulación, completar los ensayos comunes y enlazar sus resultados con fotos, videos y logs.

## 31. Coherencia de entrega

Los archivos se vinculan desde su sección correspondiente y se incluye inventario con SHA-256. Se conservan los originales y sus licencias. El firmware debe compararse con la versión efectivamente demostrada antes de la entrega académica final. [Consultar matriz de cumplimiento]({{ '/10-rubrica/' | relative_url }}).
