## **SCT013-000 (100A:50mA) estabilidad y reducción de ruido para tarjeta arduino uno:**
* Conectar resistencia de carga de 33 Ω entre el cable positivo del SCT013-000 (generalmente rojo) y la tierra (GND) del Arduino. voltaje correcto para Arduino.
* Conectar un condensador de 10uF y 16V (o más) entre el cable positivo del SCT013-000 (el mismo punto donde se conecta la resistencia de carga) y la tierra (GND) del -Arduino. Asegúrate de conectar el lado negativo del condensador (la línea marcada en el condensador) al GND. Para filtrar el ruido y estabilizar la señal.
* Conectar un divisor de voltaje formado por dos resistencias de igual valor (por ejemplo, dos resistencias de 10kΩ) en serie entre la alimentación de 5V del Arduino y la tierra (GND). Conecta el punto medio de este divisor (el punto donde se conectan las dos resistencias) al cable positivo del SCT013-000, en el mismo punto donde se conecta la resistencia de carga.
* Conectar el cable positivo del SCT013-000 al pin analógico del Arduino (por ejemplo, A0). Este pin leerá el voltaje proporcional a la corriente medida por el sensor.
* Conectar el cable negativo del SCT013-000 (generalmente negro) a la tierra (GND) del Arduino.



## **ZMPT101B para medir voltajes de CA alrededor de 110 V:**

* **Divisor de tensión:**  Como el Arduino puede leer de 0 a 5V en sus pines analógicos, y el ZMPT101B tiene un ratio 1:1, puedes utilizar un divisor de tensión con resistencias de igual valor (por ejemplo, dos resistencias de 10kΩ) para reducir la tensión a un nivel seguro para el Arduino.
* **Filtrado de ruido:** Para reducir el ruido, añade un filtro de paso bajo de primer orden utilizando un condensador y una resistencia. Conecta una resistencia (por ejemplo, 10kΩ) en serie con la salida del divisor de tensión y luego conecta un condensador (por ejemplo, 100nF) desde el punto de conexión entre la resistencia y el divisor de tensión a tierra (GND). Esto ayudará a eliminar las frecuencias de ruido más altas.
* **Desplazamiento de nivel:** Dado que la señal de CA del ZMPT101B oscila alrededor de 0V, necesitarás desplazarla para que oscile alrededor de 2.5V, lo que permite al Arduino leer correctamente la señal. Conecta otro divisor de tensión formado por dos resistencias de igual valor (por ejemplo, dos resistencias de 10kΩ) entre la alimentación de 5V del Arduino y la tierra (GND). Conecta el punto medio de este divisor (el punto donde se conectan las dos resistencias) a la salida del filtro de paso bajo (después de la resistencia de 10kΩ mencionada en el paso 2).
* **Conexión al pin analógico de Arduino:** Conecta la salida del desplazamiento de nivel al pin analógico de Arduino (por ejemplo, A1). El Arduino leerá el voltaje proporcional al voltaje de entrada medido por el sensor.


* **ZMPT101B -> Divisor de tensión -> Filtro de paso bajo -> Desplazamiento de nivel -> Pin analógico de Arduino (A1)**
* **GND (tierra) de Arduino conectado a la tierra del circuito y el divisor de tensión de desplazamiento de nivel.**
* **VCC (5V) de Arduino conectado al divisor de tensión de desplazamiento de nivel.**
