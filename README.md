# MentorBit-PIR

Esta librería está construida por Digital Codesign para utilizar el módulo PIR, principalmente diseñado para el kit educacional "MentorBit".

Puedes encontrar nuestro MentorBit y mucho más material de electrónica y robótica en nuestra tienda oficial: [https://digitalcodesign.com/shop](https://digitalcodesign.com/shop)

# Modo de empleo

Una vez tengamos la librería instalada desde el Arduino IDE, tenemos que incluir la librería con la siguiente línea:

```
#include <MentorBitPir.h>
```

### Constructor

Una vez incluida la librería, usamos el constructor para crear el objeto del módulo PIR, y definir el pin al que está conectado el sensor PIR:

```
MentorBitPir pir(PIN_PIR);
```

Donde `PIN_PIR` es el pin al que está conectado el sensor PIR.

### Uso

Con el objeto `pir` definido, podemos obtener la lectura digital del sensor utilizando la función `lecturaDigital()`, que devuelve un valor de tipo `bool`:

```
bool valor = pir.lecturaDigital();
```

El valor devuelto será `true` si el sensor detecta movimiento y `false` si no hay movimiento.
