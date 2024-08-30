# Introducción:

# Chasis: 

# 1. Chasis del Carro Autónomo

El chasis de un carro autónomo es la estructura fundamental que sostiene todos los componentes electrónicos y mecánicos necesarios para su funcionamiento. En un diseño típico para un carro autónomo, el chasis puede ser una estructura de plástico, metal o material compuesto que ofrece la resistencia necesaria y al mismo tiempo es lo suficientemente ligero para no sobrecargar los motores. En este caso, el carro está diseñado para operar de manera autónoma utilizando un sistema basado en Arduino, junto con una serie de sensores y actuadores que le permiten percibir su entorno y tomar decisiones.

# Características Clave del Chasis:
-  Material: Generalmente hecho de plástico o metal ligero.
-   Diseño: Debe permitir el montaje de sensores, motores y componentes electrónicos de manera segura.
-   Montaje de Ruedas: Espacios diseñados para asegurar las ruedas y los motores de tracción.
-  Aperturas: Espacios para cables y conexiones.

# 2. Parte Inferior del Chasis

La parte inferior del chasis es crucial para el montaje de los componentes de tracción y la estabilidad del carro.

- # *Motores CC:*
  Montados en la parte inferior para proporcionar movimiento al carro. Los motores de corriente continua (CC) permiten la propulsión y control de la dirección.
- # *Controlador de Motores (Driver L298N):*
  Este componente se encarga de controlar la dirección y la velocidad de los motores CC. Se conecta a los motores y recibe señales del Arduino para ajustar el movimiento.
- # *Ruedas:*
  Están conectadas a los motores CC y permiten que el carro se mueva en diferentes direcciones.

# 3. Parte Superior del Chasis

La parte superior del chasis es donde se colocan los sensores y componentes electrónicos que permiten al carro funcionar de manera autónoma.

- # *Sensor Ultrasónico:*
Este sensor mide la distancia a los objetos cercanos y ayuda al carro a evitar obstáculos. Está montado en una posición que le permite detectar objetos en el camino del carro.
- # *Sensor de Color:*
  [![imagen-2024-08-30-113657284.png](https://i.postimg.cc/3x2dtgSL/imagen-2024-08-30-113657284.png)](https://postimg.cc/w1TqvsdJ)

  Este sensor identifica el color de los objetos y puede usarse para seguir líneas o detectar señales específicas en el entorno.
- # *Cámara:*
Se utiliza para capturar imágenes o video del entorno del carro. Puede ser utilizada para el procesamiento de visión por computadora y toma de decisiones basada en imágenes.
- # *Servomotor:*
Se usa para ajustar la dirección del carro o el ángulo de los sensores, proporcionando una mayor flexibilidad en el control del movimiento.
- # *Protoboard y Cableado:*
La protoboard (o placa de pruebas) permite realizar conexiones temporales y pruebas de circuito. Los cables conectan todos los componentes al Arduino y al controlador de motores.
- # *Arduino:*
Actúa como el cerebro del carro, procesando las señales de los sensores y enviando comandos a los motores para controlar el movimiento.

# Conclusión

El chasis y la disposición de los componentes en un carro autónomo basado en Arduino son fundamentales para su funcionamiento eficaz. La parte inferior del chasis está diseñada para albergar los motores y el controlador de motores, mientras que la parte superior se destina a los sensores y componentes electrónicos. La combinación de estos elementos permite al carro autónomo navegar y tomar decisiones en su entorno de manera autónoma y precisa.

# Movimiento:

# *Chasis:*

El Robot cuenta con dos partes de mecanismos independientes, el tren delantero y el tren trasero:

- # Tren delantero:

Se decidió que el carro autónomo tuviera tracción trasera en lugar de delantera. El carro está equipado con un sistema de dirección basado en un servomotor, que permite ajustes precisos en la orientación de las ruedas. Se optó por usar un servomotor estándar en lugar de motores paso a paso debido a su capacidad adecuada para maniobras en el espacio reducido del carrito. Aunque el servomotor seleccionado no cuenta con un torque específico como el MG995, su diseño facilita un control eficiente del movimiento y dirección, gracias a la integración con los motores CC y el controlador de motores L298N. Esta configuración permite una maniobrabilidad adecuada, favorece el seguimiento de la pista circular y la evitación de obstáculos, mientras mantiene la simplicidad en el control y ajuste del carrito.

- # Tren trasero:

El movimiento de las ruedas traseras se transmite del actuador (motor de CC) a las ruedas mediante un sistema de engranajes de 36 mm de diámetro, colocados en un eje hexagonal. Esta configuración permite una transmisión de movimiento efectiva sin necesidad de componentes adicionales como ejes circulares. Los motores de CC utilizados en el carro tienen un torque adecuado para la tracción, y al funcionar con una batería de 9V, la velocidad nominal de 250 rpm a 12V se reduce a aproximadamente 187 rpm, resultando en una velocidad de aproximadamente 1,37 m/s. Esta elección asegura un equilibrio entre velocidad y control en el movimiento del carro autónomo.




# Componentes:

*Lista de componentes electrónicos:*

|**Piezas**|**Cantidad**|
| :-: | :-: |
|Placa Arduino|1|
|Servomotor|1|
|Motores de CC|2|
|Controlador de Motores (L298N o L293D)|1|
|Protoboard|1|
|Cables|42|
|Sensor Ultrasónico (HC-SR04)|2|
|Sensor de Color (TCS3472)|1|
|Batería (PKCell de 9V)|2|
|Cámara (ESP32-CAM)|1|
|Eje Direccional|1|
|Ruedas|4|
|Switch|2|

# Batería:

Al adquirir un kit de robótica obtuvimos una batería de 9V, que usamos para alimentar todos los componentes del carro. La batería proporciona energía tanto al Arduino Uno como al controlador de motores L298N. El Arduino Uno puede funcionar con un voltaje de entrada de 7-12V, por lo que conectamos la batería de 9V directamente al Arduino y al controlador de motores. Los cables de alimentación se ramificaron desde la batería para suministrar energía a estos componentes, asegurando el funcionamiento del sistema.

# Controlador (Arduino 1):

Se eligió usar el Arduino Uno para el proyecto debido a su equilibrio entre funcionalidad y simplicidad. El Arduino Uno, con sus 14 pines digitales y 6 pines analógicos, proporciona suficiente capacidad para manejar los sensores y actuadores del carro. Además, su compatibilidad con I2C permite conectar varios componentes sin complicaciones adicionales. Aunque tiene menos pines y recursos que otros modelos como el Arduino Mega, su facilidad de uso y capacidad para manejar el procesamiento necesario hacen del Arduino Uno una opción adecuada para este proyecto.

# CÓDIGO:                                                                                                                                                                                                                                                                                                                            

# Motor cc:

[![AR2870-AR0110-V1.jpg](https://i.postimg.cc/pXb5bW9c/AR2870-AR0110-V1.jpg)](https://postimg.cc/5jg28MS8)

|***Tensión nominal***|`       `***12V***|
| :- | :- |
|***Potencia nominal***|`       `***8.3***|
|***Corriente de arranque***|`      `***1.5A***|
|***Reducción***|`    `***18.8:1***|
|***Velocidad sin carga:***|`   `***320 rpm***|
|***Velocidad nominal:***|***    ***224 rpm***|
|***Corriente sin carga:***|***   ***≥120 mA***|
|***Corriente nominal:***|***    ***≥400 mA***|
|***Par máximo:***|`  `***3.1 kg·cm*** |
|***Par nominal:***|***  ***0.67 kg·cm***|

Con el kit adquirido, aprovechamos varias piezas útiles, como los motores, sus bases y las ruedas. Cada motor, diseñado para operar a 12V, tiene una velocidad nominal de 250 rpm y un par de 3.5 kg·cm. Por lo tanto, utilizando un solo motor a 9V, es suficiente para proporcionar la velocidad, el control y el seguimiento necesarios. Además, el encoder incorporado en el motor nos ofrece una mayor precisión en el recorrido que el robot debe realizar en el campo.

# SERVO MOTOR SG90:

[![descarga.jpg](https://i.postimg.cc/fRY62vGg/descarga.jpg)](https://postimg.cc/xXTxqLTK)

Hemos optado por el servomotor MG995 debido a su alto par motor en un tamaño compacto. Este modelo supera a su predecesor, el SG90, ofreciendo una dirección mucho más precisa con un par de 9 kg·cm a 5V.

# Sensor ultrasonico HC-SR04:

![Librería sensor ultrasónico HC-SR04 - MPLAB X - INTESC](Aspose.Words.2ad2f250-2836-4d0f-b14d-29fd808ad11a.004.jpeg)





|***Voltaje de trabajo***|***Corriente de trabajo***|***Frecuencia de trabajo***|***Distancia mínima***|***Distancia máxima***|***Ángulo de medición:***|***Pulso Trigger (entrada)***|***Pulso Echo (salida)***|
| :- | :- | :- | :- | :- | :- | :- | :- |
|5V DC|15 mA|40 Hz|2 cm|4 m|<p>`       `15°</p><p></p>|***    10 μs TTL|100-25000 μs TTL|



Los sensores ultrasónicos HC-SR04 permiten calcular distancias utilizando ondas ultrasónicas. Un emisor transmite una onda que es detectada por un receptor, y a partir del tiempo que tarda el eco en regresar, el sensor calcula la distancia al objeto. Estos sensores permiten al robot tener una estimación precisa de su ubicación en la cancha, dado que tienen una capacidad de detección máxima de 4 m, que es adecuada para una cancha de 3x3 m. Además, el sensor ayuda a detectar posibles obstáculos y evitar colisiones, mejorando la navegación del robot.
