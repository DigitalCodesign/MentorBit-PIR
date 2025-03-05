# MentorBitPir

Librería para la detección de movimiento mediante sensor PIR en módulos compatibles con MentorBit.

## Descripción

La librería `MentorBitPir` facilita la detección de movimiento utilizando un sensor PIR (Passive Infrared) en módulos compatibles con MentorBit. Permite detectar la presencia de personas, animales u objetos en movimiento dentro del rango del sensor, ideal para aplicaciones de seguridad, automatización del hogar y proyectos interactivos.

## Modo de Empleo

1.  **Instalación:**
    * Abre el IDE compatible con MentorBit.
    * Ve a "Herramientas" -> "Gestionar librerías..."
    * Busca "MentorBitPir" e instálala.

2.  **Ejemplo básico:**

    ```c++
    #include <MentorBitPir.h>

    MentorBitPir pir(2); // Sensor PIR conectado al pin 2

    void setup() {
      Serial.begin(9600);
      Serial.println("Sensor PIR inicializado.");
    }

    void loop() {
      if (pir.lecturaDigital()) {
        Serial.println("Movimiento detectado!");
      }
      delay(100);
    }
    ```

## Constructor y Métodos Públicos

### Constructor

* `MentorBitPir(uint8_t pin_pir = 0)`: Crea un objeto `MentorBitPir`.
    * `pin_pir`: Número de pin digital al que está conectado el sensor PIR. Si no se especifica, se asume que no está conectado a ningún pin inicialmente.

### Métodos

* `bool lecturaDigital()`: Devuelve `true` si se detecta movimiento, `false` en caso contrario.
