# MentorBit-PIR

Esta librería está diseñada para que puedas detectar movimiento en tu entorno usando tu placa MentorBit y el **módulo PIR**.

Si estás empezando en el mundo de la electrónica, ¡no te preocupes! MentorBit está pensado para que aprender sea fácil y divertido. Esta placa ya incluye un montón de componentes (LEDs, pulsadores, pantallas, etc.) y utiliza conectores especiales (JST) para que puedas añadir nuevos sensores y módulos sin tener que pelearte con un montón de cables. Pásate por nuestra web para saber más de MentorBit y nuestros productos [pinchando aquí](https://digitalcodesign.com/).

![Render del Módulo MentorBit de Presencia PIR.](https://github.com/DigitalCodesign/MentorBit-PIR/blob/main/assets/PIR_Module.png)

Con esta librería, podrás detectar la presencia de personas u objetos en movimiento y usar esa información para automatizar tus proyectos.

---

## Descripción

### ¿Qué es un sensor PIR?

Un sensor **PIR (Passive InfraRed)** detecta cambios en el calor infrarrojo del entorno. Es decir, cuando una persona u objeto caliente pasa por delante del sensor, este detecta ese cambio y lo interpreta como presencia o movimiento.

Este tipo de sensor es muy usado en alarmas, luces automáticas, sistemas de ahorro energético y más, ya que es económico, de bajo consumo y fácil de usar.

---

### ¿Qué hace esta librería?

La librería **MentorBit-PIR** te permite interactuar con el sensor PIR de forma sencilla. Internamente gestiona la lectura del pin digital y ofrece funciones claras para que puedas saber si se ha detectado movimiento.

---

### ¿Qué puedes construir con este módulo?

- Un sistema de luces automáticas que se encienden al detectar presencia.
- Alarmas que se activan al detectar movimiento.
- Dispositivos interactivos que reaccionan al acercarse una persona.

---

## Cómo empezar

### 1. **Conexión del Módulo**

Conecta el módulo PIR a uno de los puertos digitales JST de 4 pines que estan en la sección "Puertos para Módulos" de la placa MentorBit. Usa el pin digital del puerto para la señal de detección.

### 2. **Instalación de la Librería**

- Abre tu entorno de programación IDE de Arduino.
- Ve al menú *Programa -> Incluir Librería -> Administrar Librerías...*
- En el buscador, escribe ***MentorBit-PIR*** y haz clic en "Instalar".

![Ejemplo de búsqueda en el gestor de librerías del IDE de Arduino.](https://github.com/DigitalCodesign/MentorBit-PIR/blob/main/assets/library_instalation_example.png)

---

## Ejemplo Básico: Detectar presencia

Este ejemplo imprime en el monitor serie si el sensor detecta movimiento.

```cpp
#include <MentorBitPIR.h>

// Definimos el pin al que conectamos la señal del sensor PIR
#define PIR_PIN 24

// Creamos el objeto del sensor
MentorBitPIR pir(PIR_PIN);

void setup() {
    // Inicializar el monitor serial a 9600 baudios
    Serial.begin(9600);
    Serial.println("Test sensor PIR listo.");
}

void loop() {
    if (pir.lecturaDigital()) {
        Serial.println("¡Movimiento detectado!");
    } else {
        Serial.println("Sin movimiento.");
    }
    delay(1000);
}
```

---

## Funciones Principales

- `bool lecturaDigital()`  
  Devuelve `true` si se ha detectado movimiento, `false` si no.

---

## Recursos Adicionales

- [Web del fabricante](https://digitalcodesign.com/)
- [Tienda Online de Canarias](https://canarias.digitalcodesign.com/shop)
- [Tienda Online de Península](https://digitalcodesign.com/shop)
- [Web Oficial de MentorBit](https://digitalcodesign.com/mentorbit)
- [Web Oficial del Módulo PIR](https://canarias.digitalcodesign.com/shop/00038904-mentorbit-modulo-pir-8121?category=226&order=create_date+desc#attr=)
- [Manual de usuario del Módulo](https://drive.google.com/file/d/1XXQpqRfjOTEkiCTRBvKzXNLK9Z7gh8ol/view?usp=drive_link)
- [Modelo 3D del Módulo PIR en formato .STEP](https://drive.google.com/file/d/1-O-Faq4cXuUIZpQK-bosTIl5Kqy8SQl8/view?usp=drive_link)
