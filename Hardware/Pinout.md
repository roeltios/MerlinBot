# Merlin Bot: Diagrama de Conexiones y Pinout (v1.0)

Este documento describe la asignación de pines del ESP32 DevKit V1 para el control de los periféricos de Merlin Bot. Se han seleccionado pines que no interfieren con el proceso de arranque (boot) del microcontrolador.

---

## 1. Sensor Ultrasónico (HC-SR04)

El sensor debe alimentarse con 5V provenientes del regulador LM2596. Aunque el ESP32 funciona a 3.3V, el pin de Echo suele tolerar la señal del HC-SR04, pero se recomienda precaución.

| Pin Sensor | Pin ESP32 (GPIO) | Función | Color de Cable (Sugerido) |
| :--- | :--- | :--- | :--- |
| VCC | 5V (Externo) | Alimentación 5V | Rojo |
| TRIG | GPIO 5 | Disparo de pulso | Naranja |
| ECHO | GPIO 18 | Recepción de pulso | Amarillo |
| GND | GND | Tierra Común | Negro |

---

## 2. Driver de Motores (L298N)

Para el control de los motores, utilizamos dos pines por motor: uno para la velocidad (PWM) y otro para la dirección.

### Motor Izquierdo (A)
| Pin Driver | Pin ESP32 (GPIO) | Función |
| :--- | :--- | :--- |
| ENA | GPIO 12 | Velocidad (PWM) |
| IN1 | GPIO 14 | Dirección |

### Motor Derecho (B)
| Pin Driver | Pin ESP32 (GPIO) | Función |
| :--- | :--- | :--- |
| ENB | GPIO 13 | Velocidad (PWM) |
| IN3 | GPIO 27 | Dirección |

---

## 3. Alimentación del Sistema

Es fundamental que todas las tierras estén unidas para que las señales lógicas tengan una referencia común.

* **Entrada de Voltaje (VIN):** Conectar a la salida de **5.0V** del regulador LM2596.
* **Tierra (GND):** Conectar al bus de tierra de la protoboard donde también terminan los negativos de las baterías y del driver.

---

## 4. Notas Técnicas de Seguridad

* **Pines de Arranque:** Se han evitado los pines GPIO 0, 2 y 15 para garantizar que el ESP32 inicie el programa correctamente al encenderse.
* **Puentes en L298N:** Asegurarse de que los puentes (jumpers) de los pines ENA y ENB del driver sean removidos para poder conectar los cables hacia los pines PWM del ESP32.
* **Multímetro:** Verificar la salida del regulador LM2596 cada vez que se cambien las baterías antes de encender el interruptor principal.
