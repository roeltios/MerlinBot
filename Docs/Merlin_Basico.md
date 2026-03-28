🔩 Merlin Bot: Especificaciones de Hardware (v1.0 Basic)

Esta es la configuración mínima necesaria para tener un robot funcional, modular y de bajo costo.
📦 Lista de Materiales (BOM)
1. Electrónica Principal

    Microcontrolador: ESP32 DevKit V1 (30 pines). Elegido por su capacidad de conectarse a la Web App vía Web Serial y su potencia para futuros proyectos de IoT.

    Driver de Motores: Módulo L298N (Puente H). Permite controlar la velocidad (PWM) y dirección de dos motores de corriente continua.

    Sensor de Distancia: HC-SR04 (Ultrasónico). Proporciona la capacidad de "ver" obstáculos mediante pulsos de sonido.

2. Sistema de Locomoción

    Motores: 2 x Motorreductores amarillos (1:48). Estándar en robótica educativa por su torque y facilidad de montaje.

    Ruedas: 2 x Ruedas de goma de 65mm.

    Apoyo: 1 x Rueda loca (Caster wheel) metálica o plástica para el tercer punto de apoyo.

3. Energía y Regulación

    Baterías: 2 x Li-ion 18650 (3.7V c/u). Proporcionan una autonomía superior a las pilas AA.

    Soporte: Portabaterías dual para 18650.

    Regulador de Voltaje: LM2596 (Step-Down). Configurado a 5V para alimentar el ESP32 y el sensor desde los 7.4V-8.4V de las baterías.

4. Estructura y Conexión

    Chasis: Placa de rejilla universal (MDF o Acrílico) con perforaciones de 3mm cada 10mm.

    Protoboard: 1 x Mini Protoboard (170 puntos) o 400 puntos, montada en la parte superior para prototipado rápido.

    Cables: Jumpers tipo Dupont (Macho-Macho y Macho-Hembra).

📐 Guía de Montaje Sugerida

Para mantener el centro de gravedad bajo y facilitar el aprendizaje en CreaEduu, se recomienda la siguiente distribución:

    Nivel Inferior: Motores y portabaterías (atrás), Rueda loca (adelante).

    Nivel Superior: Protoboard al centro, Driver L298N en la parte posterior y ESP32 en la protoboard.

    Frente: Sensor ultrasónico montado con un soporte simple orientado hacia adelante.

⚡ Requerimiento de Seguridad Previo

    IMPORTANTE: Antes de realizar cualquier conexión al ESP32, se debe girar el potenciómetro del regulador LM2596 mientras se mide con un multímetro hasta que la salida marque 5.0V.
