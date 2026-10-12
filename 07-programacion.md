---
permalink: /07-programacion/
layout: default
title: Programación e interfaz
nav_order: 8
---

# Programación e interfaz

## 19. Arquitectura del software

El firmware `Brazos_Gemelos.ino`, organizado con un archivo de configuración editable, integra adquisición analógica, detección táctil, selección de modo, generador de consignas y salida PCA9685. El servidor HTTP y su página están incorporados en el mismo archivo. La versión de esta práctica conserva el mapeo de conexiones y agrega consulta de estado por serie y HTTP.

![Flujo de ejecución]({{ '/assets/diagrams/flujo.png' | relative_url }})

## 20. Ley de operación

Cada joystick controla **velocidad de cambio de consigna**, no un ángulo absoluto. El filtro discreto es `f ← f + 0.30·(ADC − f)`. Se resta el centro calibrado y se aplica zona muerta de 280 cuentas. Fuera de ella se normaliza la desviación con el recorrido disponible a cada lado del centro.

`q[k+1] = saturar(q[k] + u[k] · sentido · velocidad_max · dt, mínimo, máximo)`

El bucle actualiza aproximadamente cada 20 ms y limita `dt` a 0.04 s. La velocidad máxima es 25°/s en bases y 20°/s en los demás ejes. La consigna inicial es 90° y los límites provisionales son 60–120°. El pulso se calcula con `1000 + (2000 − 1000)·q/180` µs; por tanto, esos límites iniciales producen aproximadamente 1333–1667 µs, no todo el intervalo 1000–2000 µs. Estos valores deben calibrarse para los servos y mecanismos reales.

La realimentación de posición interna del servo no llega al programa: `angleDeg` almacena la orden, no una medición de la articulación.

## 21. Interfaz y procedimiento de operación

### Control manual

1. Verificar polaridad, GND común, distribución CH0–CH7 y tensión nominal de servos. Centrar servos inicialmente sin acoplar mecanismos para ajustar horns y límites.
2. Encender ESP32 y fuente externa. No tocar electrodo y dejar joysticks centrados durante los tres segundos de calibración.
3. Abrir monitor serie a 115200 bit/s. Comprobar `MANUAL listo` y ausencia de errores de PCA9685 o centro.
4. Mantener todos los ejes al centro hasta habilitación (400 ms). Mover J1/J3 en X para base, en Y para codo; J2/J4 en Y para hombro y en X para pinza.
5. Centrar un eje detiene el incremento angular y mantiene su consigna. Calibrar `JOY_DIR`, `SERVO_DIR`, `MIN_DEG` y `MAX_DEG` individualmente; no forzar topes.

### Control remoto

1. Tocar el electrodo GPIO4 al menos 180 ms y soltar. El sistema crea su AP.
2. Conectarse a **Brazos_Gemelos**, contraseña **Brazos2026**.
3. Abrir **http://192.168.4.1** en el navegador del dispositivo conectado. No requiere internet.
4. Mantener pulsado uno de los 16 botones para mover un servo; soltar para detener. La implementación remota permite **un eje a la vez**.
5. Sin cliente o sin comandos durante más de 450 ms, se detiene el incremento de consigna. El servo conserva par: no es un paro eléctrico de emergencia.
6. Otro toque vuelve a manual, desconecta la red y exige centrar todos los joysticks antes de habilitar.

### Vista de la interfaz incluida en el firmware

<iframe title="Vista demostrativa de la interfaz del firmware" src="{{ '/interfaz-demo.html' | relative_url }}" width="100%" height="750"></iframe>

Esta vista se extrae del HTML original y permite revisar la disposición y etiquetas. **Es demostrativa: no conecta ni envía órdenes a un robot.** No sustituye una captura real de la sesión AP; esa evidencia de operación aún debe adjuntarse.

## 22. Librerías y dependencias

| Recurso | Función | Versión / trazabilidad |
|---|---|---|
| Arduino core ESP32 (Espressif) | Arduino.h, Wire, WiFi, WebServer, esp_system | Versión exacta de compilación anterior no registrada |
| Adafruit PWM Servo Driver Library | PCA9685, frecuencia y pulsos | Versión exacta anterior no registrada; instalar con gestor |
| Adafruit BusIO | Dependencia del controlador | Versión exacta anterior no registrada |
| Arduino IDE | Compilar y cargar ESP32 Dev Module | Versión anterior no registrada |
| Navegador con WebGL | Visor STL propio sin librerías externas | JavaScript ES2015+, WebGL 1 |
| HTML estático y CSS local | Reporte navegable; estilos basados en el sitio original | Sin compilación ni dependencias de red para visualizar |

El reporte no inventa versiones empleadas. Para cerrar la reproducibilidad, registrar versiones del core/IDE y bibliotecas, exportar el log de compilación en `registros/dependencias.csv`. [Código oficial del driver](https://github.com/adafruit/Adafruit-PWM-Servo-Driver-Library) y [core oficial ESP32](https://github.com/espressif/arduino-esp32).

## 23. Organización en funciones

| Bloque | Responsabilidad |
|---|---|
| `setup()` | I²C, PCA9685, salidas, calibración de 100 muestras, consigna inicial y rutas HTTP |
| `loop()` | Selecciona adquisición según modo, integra velocidades y actualiza servos |
| `updateTouch()` | Muestreo cada 25 ms, histéresis y validación de 180 ms |
| `changeMode()` | Detiene incremento, enciende/apaga AP, reinicia habilitación manual |
| `writeServo(ch)` | Convierte consigna angular a microsegundos y transmite al PCA9685 |
| `stopMotion()` | Borra el canal/dirección activos de remoto; no desconecta alimentación |
| Ruta `/` | Sirve HTML y renueva token de sesión |
| Ruta `/cmd` | Valida token, secuencia, canal y dirección; actualiza comando |
| `send()` / `release()` del navegador | Renovación de comandos cada 100 ms y liberación de botones |

## 24. Código fuente descargable y ejecución

La carpeta Arduino contiene el programa y `Config.h`, donde se ajustan pines, sentidos, velocidades, pulsos y límites. En el monitor serie, enviar `?` muestra modo y consignas. En remoto, `/status` devuelve esas consignas en JSON. No son mediciones de posición.


[Ver archivo principal .ino]({{ '/firmware/Brazos_Gemelos/Brazos_Gemelos.ino' | relative_url }}) · [Descargar carpeta Arduino en ZIP]({{ '/assets/files/Brazos_Gemelos.zip' | relative_url }})

1. Descargar el ZIP, extraer la carpeta `Brazos_Gemelos` y abrir el `.ino` del mismo nombre. Conservar `Config.h` junto al programa.
2. En Arduino IDE instalar el core ESP32 de Espressif y las bibliotecas Adafruit PWM Servo Driver y BusIO.
3. Seleccionar **ESP32 Dev Module**, puerto correspondiente y verificar compilación. El programa rechaza por preprocesador otras familias.
4. Cargar, comprobar mensajes de arranque y seguir la calibración mecánica antes de acoplar cargas.
5. Guardar versiones y log de compilación junto con resultados de prueba.

