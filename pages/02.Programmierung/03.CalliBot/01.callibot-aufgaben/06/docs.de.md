---
title: 'Calli:Bot folgt einer schwarzen Linie'
taxonomy:
    category:
        - docs
---

Der Calli:Bot kann fahren und erkennt, ob ein Hindernis vor ihm ist. Nun wollen wir mit Hilfe der Liniensensoren auf der Unterseite, den Calli:Bot einer schwarzen Linie folgen lassen.
![alt](./line.png)

1. Die Liniensensoren testen, ob sie unter sich etwas dunkles oder etwas helles sehen. Die Logik wäre, dass wenn der linke Liniensensor etwas dunkles sieht (=schwarze Linie), soll er den linken Motor kurz stoppen, sodass er nicht über die Linie fährt und sich diese immer genau in der Mitte des Calli:Bots befindet. Der rechte Sensor soll mit dem rechten Motor genauso verfahren.

2. Öffne den [MakeCode Editor](https://makecode.calliope.cc/) und nutze eine Bedingung mit Alternative, die testet, ob die Lichtsensoren etwas dunkles unter sich wahrnehmen:
![alt](./line2.png)

3. Kannst du das Programm vervollständigen, sodass der linke Motor kurz stoppt, wenn der linke Liniensensor etwas dunkles sieht und dass der rechte Motor kurz stoppt, wenn der rechte Liniensensor etwas dunkles sieht?

### Liniensensor:
Die Linienensoren sind auf der Unterseite des Calli:Bots angebracht. Sie können die Helligkeit der Unterlage registrieren und geben den Wert 0 oder 1 zurück.
- 1 bedeutet = hell
- 0 bedeutet = dunkel

Die Codeblöcke aus dem [MakeCode Editor](https://makecode.calliope.cc/) registrieren "hell" oder "dunkel". Im Hintergrund wandeln die Blöcke aber auch die 1 oder 0 um. Der Code hinter den Blöcken ist auf GitHub zu finden:  [Calli:Bot Blöcke Code](https://github.com/Sulkar/Callibot/blob/master/Knotech.ts)

Besonders hervorzuheben ist die Definition zu den Liniensensoren:

```javascript
//="Liniensensor $sensor"
//% blockId K_readLineSensor color="#00C040" block="Liniensensor |%sensor| |%status"
export function readLineSensor(sensor: KSensor, status: KSensorStatus): boolean {
    let result = false

    let buffer = pins.i2cReadBuffer(0x21, 1);
    KInit();
    if (sensor == KSensor.links) {
        buffer[0] &= 0x02
    }
    if (sensor == KSensor.rechts) {
        buffer[0] &= 0x01
    }
    switch (status) {
        case KSensorStatus.hell:
            if (buffer[0] != 0) {
                result = true
            }
            else {
                result = false
            }
            break
        case KSensorStatus.dunkel:
            if (buffer[0] == 0) {
                result = true
            }
            else {
                result = false
            }
            break
    }
    return result
}
```