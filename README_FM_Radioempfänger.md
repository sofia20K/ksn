# KSN - Arbeitsauftrag 5CHEL



### Thema: FM-Radioempfänger

### Genauere Beschreibung:
Ein FM-Radioempfänger empfängt Signale, die mit der Frequenzmodulation (FM) moduliert sind. 
In FM-Radiosendern wird die Information durch die Änderung der Frequenz des Trägersignals übertragen. 
Der Empfänger demoduliert das zuvor modulierte Signal, um die ursprüngliche Information (z. B. Musik oder Sprache) wiederherzustellen.

### Mitglieder
- Sofia Katundi
- Stefan Ruzic
- Emilio Gahr

### Abgabetag: 10.04.2024

## Arbeitsprotokoll 

##### Aufbau des FM-Receivers:

Die Blöcke müssen wie in der Abbildung ersichtlich verbunden werden.

##### Erklärung zu den Blöcken:

Der File Source-Block liest die Audiodatei aus der Angabe ein.

Der Multiply-Block multipliziert den Signal Source-Block mit dem File Source-Block, um den Radiosender in die Mitte des Spektrums zu verschieben.

Der Frequency Sink-Block und der Waterfall Sink-Block dienen dazu, die Ausgabe als Spektralanzeige und als Wasserfalldiagramm zu visualisieren.

Der QT GUI Range-Block, dient dazu, die Frequenz beim Signal Source und bei den Sinks zu verändern.

Der Low Pass Filter-Block trennt die Signale.
Der WBFM Receive-Block demoduliert das FM-Signal.
Der Audio Sink-Block dient dazu, die demodulierte Audio abzuspielen.

##### Konfigurieren der Parameter:
Tiefpassfilter: Grenzfrequenz (40 kHz.)
QT GUI Range-Block: Mittenfrequenz (91 MHz) (Start: 88.5M (-2.5M), Stop:93.5M(+2.5M)). 
Samplerate bei allen Blöcken: 5 MHz

## Ergebnis
Das Ergebnis sollte ein hörbares Audioausgangssignal sein, dass den eingestellten Radiosender wiedergibt.

###### Abbildung 1
![WhatsApp Bild 2024-04-09 um 22 55 15_a82a8d00](https://github.com/sofia20K/ksn/assets/165880295/8651203d-f50b-40b3-9f11-9046e0bbaff3)

###### Abbildung 2

![WhatsApp Bild 2024-04-09 um 22 56 50_948d66e6](https://github.com/sofia20K/ksn/assets/165880295/91a05cac-1f1d-4212-82f7-ab048a35b305)

###### -> Nur ein Rauschen kein schöner Sound

