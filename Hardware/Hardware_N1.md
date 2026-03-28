# Merlin Bot Nivel 1: Actuadores y Expresión (Alfa)

Este nivel inicial se enfoca en la salida de datos y el control físico. El objetivo es que el alumno comprenda cómo el microcontrolador ejecuta instrucciones para interactuar con el mundo real.

## Componentes Principales
* **Cerebro:** ESP32 DevKit V1.
* **Movimiento:** Driver L298N + 2 Motores DC (1:48).
* **Interfaz Visual:** Pantalla OLED I2C (0.96").
* **Energía:** 2 Baterías 18650 + Regulador LM2596 (Ajustado a 5V).

## Objetivos Pedagógicos
1. **Control Secuencial:** Programar rutas de movimiento predefinidas (avanzar 2 segundos, girar, retroceder).
2. **Gestión de Velocidad:** Introducción al concepto de PWM para aceleración y frenado suave.
3. **Comunicación Visual:** Mostrar estados del robot, nombres o iconos básicos en la pantalla OLED.

## Primer Reto
Programar a Merlin para que dibuje una figura geométrica en el suelo mientras muestra el nombre del movimiento en la pantalla.cajas apilables
