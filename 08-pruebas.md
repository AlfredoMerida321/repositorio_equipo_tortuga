---
permalink: /08-pruebas/
layout: default
title: Integración y pruebas
nav_order: 9
---

# Integración y pruebas

## 25. Integración física

![E01 — montaje completo]({{ '/assets/img/practica01/sistema-completo.png' | relative_url }})

**E01:** ambos mecanismos se apoyan sobre un tablero común. Se observan cuatro joysticks, ESP32 con borneras, módulo convertidor y mazos a servos. Faltan fotos de detalle de la distribución de potencia, identificación CH0–CH7 y sujeción final del cableado. No se puede confirmar la continuidad eléctrica solo con esta vista.

## 26–28. Protocolo y resultados

Los siguientes criterios son **propuestos para el ensayo**, no resultados observados. Utilizar el mismo objeto, posiciones marcadas, alimentación y condiciones para las dos versiones. Identificar cada evidencia por nombre de archivo y fecha.

| ID | Prueba | Procedimiento | Aceptación / registro | Estado |
|---|---|---|---|---|
| T01 | Alimentación | Medir lógica y potencia en reposo y movimiento | Valores dentro de fichas; sin reinicios | Pendiente |
| T02 | I²C y PWM | Arranque y medición en ocho canales | PCA detectado; periodo cercano a 20 ms | Pendiente |
| T03 | Joysticks | Accionar cada uno de los ocho ejes por separado | Solo se mueve el canal asignado, sentido correcto | Pendiente |
| T04 | Centro estable | Soltar controles 30 s tras calibrar | Sin incremento de consigna; observar deriva mecánica | Pendiente |
| T05 | Movilidad | Barrer de forma gradual el rango calibrado sin carga | Sin colisiones, bloqueo ni cables tensos; registrar grados de consigna | Pendiente |
| T06 | Touch | Realizar 10 cambios manual/remoto | Un cambio por toque y retorno correcto | Pendiente |
| T07 | Remoto | Conectar AP y probar los 16 botones | Respuesta del servo correcto al mantener/soltar | Pendiente |
| T08 | Pérdida de enlace | Mover un eje y desconectar cliente | Cesa incremento tras caducidad; registrar tiempo, par permanece | Pendiente |
| T09 | Retorno manual | Volver desde remoto con una palanca desviada | No habilita hasta neutro estable por 400 ms | Pendiente |
| T10 | Agarre | Cerrar sobre objeto de masa y tamaño medidos | Sostiene y libera sin deslizamiento; anotar objeto | Pendiente |
| T11 | Ciclo completo | Tomar objeto en A, elevar, girar, dejar en B y volver | 10 intentos por versión; registrar éxitos y tiempos | Pendiente |
| T12 | Repetibilidad | Volver a una marca 10 veces desde igual postura | Medir dispersión del efector en mm; no inferir de PWM | Pendiente |
| T13 | Holgura y ensamble | Inspeccionar articulaciones sin energía | Registrar juego, ajustes y fotografías | Pendiente |

### Secuencia funcional completa a documentar

Colocar un objeto identificado en A → aproximar pinza abierta → cerrar → elevar → girar a B → descender → abrir → regresar a posición inicial. Repetir por cada versión en manual y demostrar también remoto. El video debe mostrar el brazo, controles y objeto en una toma continua. Registrar caídas, asistencia manual, reinicios y contactos con topes; no eliminar intentos fallidos del conteo.

**Éxito (%) = 100 × ciclos completos / intentos.** Para tiempos, reportar media, mínimo y máximo con número de repeticiones. Para repetibilidad, reportar los puntos medidos y su dispersión respecto a la media. La exactitud requiere además un objetivo de referencia medido; no confundir ambas magnitudes.

[Descargar registro de pruebas CSV]({{ '/registros/pruebas.csv' | relative_url }}) · [Registro de fabricación]({{ '/registros/fabricacion.csv' | relative_url }})

## Evidencias disponibles

| ID | Archivo | Qué acredita | Qué no acredita |
|---|---|---|---|
| E01 | sistema-completo.png | Presencia de ambas versiones, joysticks y montaje electrónico | Continuidad, carga, precisión o modos funcionando |
| E02 | brazo-impreso.png | Ensamble mecánico de EEZYbotARM | Material exacto, parámetros o prueba funcional |
| D01 | MeArm_piezas_P1_a_P36.pdf | Referencia gráfica y numeración de piezas | CAD nativo o plano totalmente acotado |
| D02 | 17 STL originales | Geometría de referencia de EEZYbotARM | Ensamble cinemático o CAD paramétrico |
| S01 | Brazos_Gemelos.ino | Lógica, mapeo y parámetros recuperados | Coincidencia con binario cargado y ensayo físico |

`assets/videos/demo.mp4` se conserva del repositorio original, pero no se usa como evidencia de funcionamiento: no se estableció su relación con la práctica ni una fecha/identificación. Adjuntar el video real en la matriz cuando se valide su procedencia.
