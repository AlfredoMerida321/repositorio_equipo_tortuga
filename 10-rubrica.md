---
permalink: /10-rubrica/
layout: default
title: Matriz de rúbrica y archivos
nav_order: 11
---

# Matriz de rúbrica y archivos

Esta matriz revisa evidencia disponible; **no asigna una calificación ni declara cumplimiento total**. “Documentado” significa que se incluyó contenido verificable para el criterio; la valoración corresponde al docente. “Parcial” y “Pendiente” muestran lo necesario para cerrar la entrega.

| Nº | Criterio | Puntos rúbrica | Estado | Evidencia / faltante |
|---:|---|---:|---|---|
| 1 | [Problema, objetivos y requisitos]({{ '/02-descripcion/' | relative_url }}) | 3 | Documentado | Necesidad, R01–R08 y restricciones |
| 2 | [Bocetos de solución]({{ '/02-descripcion/' | relative_url }}) | 3 | Documentado | Esquema funcional y referencia del autor |
| 3 | [Alternativas y selección]({{ '/02-descripcion/' | relative_url }}) | 3 | Documentado | Tabla de decisiones técnicas |
| 4 | [Arquitectura general]({{ '/03-diagramaBloques/' | relative_url }}) | 3 | Documentado | Subsistemas y relaciones |
| 5 | [Arquitectura y dimensiones]({{ '/05-Robot3D/' | relative_url }}) | 3 | Parcial | Envolventes STL; faltan dimensiones del montaje y 2D |
| 6 | [Materiales mecánicos]({{ '/04-Robot2D/' | relative_url }}) | 4 | Parcial | Faltan cantidades de fijaciones, materiales y proveedores |
| 7 | [Editables y fabricación]({{ '/05-Robot3D/' | relative_url }}) | 4 | Parcial | STL/PDF disponibles; falta CAD nativo y archivo corte |
| 8 | [Planos de fabricación]({{ '/05-Robot3D/' | relative_url }}) | 4 | Parcial | Láminas de referencia; faltan cotas funcionales y tolerancias |
| 9 | [Registro de fabricación]({{ '/04-robot2d-proceso-ensamble/' | relative_url }}) | 3 | Pendiente | Faltan máquina, parámetros y ajustes por versión |
| 10 | [Secuencia de ensamble]({{ '/04-robot2d-proceso-ensamble/' | relative_url }}) | 3 | Documentado | Guía diagramada; sin fotos intermedias |
| 11 | [Versiones ensambladas]({{ '/08-pruebas/' | relative_url }}) | 4 | Documentado | E01 y E02 reales |
| 12 | [Pruebas mecánicas]({{ '/08-pruebas/' | relative_url }}) | 3 | Pendiente | Protocolo sin mediciones |
| 13 | [Bloques electrónicos]({{ '/06-electronica/' | relative_url }}) | 3 | Documentado | Esquema modular con potencia y lógica |
| 14 | [Materiales electrónicos]({{ '/06-electronica/' | relative_url }}) | 3 | Parcial | Faltan modelos de todos los servos y datos de fuente |
| 15 | [Esquemático editable]({{ '/06-electronica/' | relative_url }}) | 4 | Parcial | SVG modular completo según firmware; cotejar cableado real |
| 16 | [Tarjeta y fabricación]({{ '/06-electronica/' | relative_url }}) | 4 | Pendiente | Sin PCB nativa o Gerbers de tarjeta propia |
| 17 | [Manufactura electrónica]({{ '/06-electronica/' | relative_url }}) | 3 | Pendiente | Foto de integración; falta evidencia de soldadura/manufactura |
| 18 | [Pruebas por bloques]({{ '/06-electronica/' | relative_url }}) | 3 | Pendiente | Protocolo sin registros |
| 19 | [Arquitectura software]({{ '/07-programacion/' | relative_url }}) | 3 | Documentado | Módulos y flujo de señales |
| 20 | [Diagrama de flujo]({{ '/03-diagramaBloques/' | relative_url }}) | 3 | Documentado | Flujo manual/remoto y protecciones |
| 21 | [Interfaz y operación]({{ '/07-programacion/' | relative_url }}) | 3 | Parcial | Interfaz extraída y guía; falta captura de sesión real |
| 22 | [Dependencias]({{ '/07-programacion/' | relative_url }}) | 3 | Parcial | Funciones identificadas; versiones originales no registradas |
| 23 | [Organización en funciones]({{ '/07-programacion/' | relative_url }}) | 4 | Documentado | Tabla de responsabilidades |
| 24 | [Código final]({{ '/07-programacion/' | relative_url }}) | 4 | Parcial | Fuente descargable; cotejo con versión demostrada y compilación pendientes |
| 25 | [Integración física]({{ '/08-pruebas/' | relative_url }}) | 3 | Parcial | Vista general real; faltan detalles etiquetados |
| 26 | [Integración electrónica/software]({{ '/08-pruebas/' | relative_url }}) | 3 | Pendiente | Sin ensayo físico registrado |
| 27 | [Modos de operación]({{ '/08-pruebas/' | relative_url }}) | 4 | Pendiente | Manual/remoto documentados, sin demostración validada |
| 28 | [Prueba funcional completa]({{ '/08-pruebas/' | relative_url }}) | 3 | Pendiente | Falta video del ciclo y resultados |
| 29 | [Comparación versiones]({{ '/09-conclusiones/' | relative_url }}) | 3 | Parcial | Comparación documental; desempeño sin medir |
| 30 | [Conclusiones técnicas]({{ '/09-conclusiones/' | relative_url }}) | 2 | Documentado | Conclusiones limitadas a evidencia |
| 31 | [Evidencias coherentes]({{ '/10-rubrica/' | relative_url }}) | 2 | Parcial | Trazabilidad disponible; falta cerrar ensayos y fabricación |


## Entregables incluidos

- [Firmware Arduino ZIP]({{ '/assets/files/Brazos_Gemelos.zip' | relative_url }}).
- [Visor y descargas STL]({{ '/viewer.html' | relative_url }}).
- [Dimensiones calculadas CSV]({{ '/assets/files/dimensiones-stl.csv' | relative_url }}).
- [Esquemático SVG editable]({{ '/assets/diagrams/esquematico.svg' | relative_url }}).
- [Arquitectura SVG]({{ '/assets/diagrams/arquitectura.svg' | relative_url }}) y [flujo SVG]({{ '/assets/diagrams/flujo.svg' | relative_url }}).
- [Plano original MeArm PDF]({{ '/assets/files/MeArm_piezas_P1_a_P36.pdf' | relative_url }}).
- [Pruebas CSV]({{ '/registros/pruebas.csv' | relative_url }}), [fabricación CSV]({{ '/registros/fabricacion.csv' | relative_url }}) y [dependencias CSV]({{ '/registros/dependencias.csv' | relative_url }}).
- [Inventario SHA-256]({{ '/assets/files/inventario-sha256.csv' | relative_url }}).

## Evidencia que debe incorporar el equipo

1. CAD editable, archivo de corte y planos totalmente acotados de ambas versiones.
2. Parámetros reales de láser/impresora, material y fotografías del proceso.
3. Esquemático/PCB nativos de la tarjeta desarrollada y evidencia de manufactura, si la práctica exige tarjeta propia.
4. Medidas, logs de compilación con versiones y videos de ambos modos y del ciclo completo.
5. Resultados de carga, holgura, repetibilidad, tiempos y comparación bajo condiciones iguales.
