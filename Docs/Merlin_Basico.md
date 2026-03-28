# Merlin Bot: Hardware Básico (v1.0 MVP)

Este documento detalla los componentes necesarios para la construcción del Producto Mínimo Viable (MVP) de Merlin Bot. El diseño prioriza la modularidad, el bajo costo y la facilidad de reparación.

---

## Lista de Materiales (BOM)

| Categoría | Componente | Cantidad | Notas Técnicas |
| :--- | :--- | :---: | :--- |
| **Control** | ESP32 DevKit V1 (30 pines) | 1 | Microcontrolador principal con Wi-Fi/Bluetooth. |
| **Potencia** | Driver de Motores L298N | 1 | Módulo de puente H para control de dos motores DC. |
| **Sensor** | HC-SR04 (Ultrasonido) | 1 | Sensor de distancia para evasión de obstáculos. |
| **Tracción** | Motorreductor Amarillo (1:48) | 2 | Incluye llantas de goma de 65mm. |
| **Energía** | Baterías Li-ion 18650 | 2 | Celdas de 3.7V (Total 7.4V - 8.4V). |
| **Soporte** | Portabaterías 18650 x2 | 1 | Con cables para conexión en serie. |
| **Regulación** | Módulo LM2596 Step-Down | 1 | Convertidor DC-DC ajustable. |
| **Base** | Chasis de Rejilla Universal | 1 | Perforaciones de 3mm con espaciado de 10mm. |
| **Apoyo** | Rueda Loca (Caster Wheel) | 1 | Punto de apoyo frontal independiente. |
| **Conexión** | Protoboard (400 puntos) | 1 | Para prototipado sin soldadura. |

---

## Especificaciones de Ensamblaje

Para garantizar la estabilidad y el acceso educativo, se sugiere la siguiente distribución física:

### Distribución de Pesos (Planta Baja)
* **Motores y Portabaterías:** Deben situarse en la base para mantener el centro de gravedad bajo.
* **Rueda Loca:** Ubicada en el eje central delantero para permitir giros de 360 grados.

### Interfaz de Control (Planta Alta)
* **Protoboard:** Situada en la parte superior para facilitar el cambio de sensores y actuadores por parte de los alumnos.
* **ESP32:** Montado sobre la protoboard para acceso directo a los pines de entrada y salida (GPIO).

---

## Configuración Eléctrica y Seguridad

### Advertencia de Voltaje
Antes de conectar el ESP32, es mandatorio seguir este procedimiento:
1. Conectar las baterías al regulador LM2596.
2. Utilizar un multímetro en la salida del regulador.
3. Ajustar el potenciómetro hasta obtener exactamente **5.0V**.
4. Solo entonces, conectar la salida a los pines de alimentación del ESP32 (VIN y GND).

### Tierras Comunes
Para que el sistema funcione correctamente, todos los terminales de tierra (GND) del ESP32, el Driver L298N, las baterías y el sensor deben estar interconectados en un solo punto común (bus de tierra de la protoboard).

---

## Capacidades del Hardware v1.0
* Movimiento diferencial (adelante, atrás, giros).
* Medición de distancia en tiempo real (rango de 2cm a 400cm).
* Programación mediante Web Serial (MicroBlocks/Arduino Cloud).
* Autonomía aproximada de 2 a 3 horas de uso continuo.
