# KSN - Projekt 5CHEL

#### 2.Semester Projekt in der 5.Klasse

### Thema: SSB Modulation on GNU Radio

Die Einseitenbandmodulation (ESB, heute besser bekannt als SSB) ist eine spektral und energieeffiziente Modulationsart für die Sprachübertragung. Es wird häufig für analoge Funkverbindungen wie den Kurzwellenbereich von Seefunkgeräten, Langstrecken-Flugfunkgeräten, militärischen Anwendungen sowie Amateur- und Zivilfunkgeräten verwendet. SSB wurde in den 1930er Jahren von Telekommunikationsbehörden entwickelt, zunächst für die drahtgebundene Übertragung von Ferngesprächen und später auch für transkontinentale Funkverbindungen. Im analogen Sprechfunk, wie er auch heute noch im Amateurfunk üblich ist, wurde die Amplitudenmodulation (AM), die zwei Seitenbänder belegte und daher eine größere Bandbreite aufwies, in den 1960er Jahren fast vollständig durch die Einseitenbandmodulation ersetzt.

### Genauere Beschreibung:

### Mitglieder
- Sofia Katundi
- Stefan Ruzic
- Emilio Gahr

### Abgabetag: 10.04.2024

### Arbeitsprotokoll 

- 28.02.2024:
  - Aufgabenstellung erklärt bekommen
  - Kurze Einführung in GNU Radio Companion, kleine Übungen dazu

- 06.03.2024:
  - Themenfindung
  - Besprechung vom Thema
  
    
- 13.03.2023:
  - Karrieretag

- 20.03.2024:
  - Projekt erstellt
  - Dokumentation geschrieben

- 03.04.2024:
  - FM Radio verbessert
  - Projekt weitergemacht

- 10.04.2024:
  - Abgabe, Präsentation des Projekts
  - Benotung

## Dokumentation

Klassischerweise gab es drei verschiedene Methoden zur Erzeugung von SSB. Die erste Methode ist die Filtermethode, bei der ein ZF-Träger DSBSC-moduliert wird und das LSB oder USB mit einem sehr selektiven Quarzfilter entfernt wird. Meine beiden SSB-Amateurtransceiver (TR4C und K2) verwenden diese Methode. Die zweite Methode ist die Hartley- oder Phasing-Methode und die letzte Methode ist die Weaver-Methode. Abbildung 1 zeigt den SSB-Modulator nach der Hartley-Phasing-Methode. Der Aufbau ist analog zum Hartley-IQ-SSB-Empfänger, der im vorherigen Beitrag beschrieben wurde. Die Sprachsignale werden zunächst für SSB-Qualität auf ca. 300-2700 Hz tiefpassgefiltert. Dann werden sie zwei symmetrischen I- und Q-Mischern zugeführt. Das Audiosignal im I-Zweig wird mit einer Hilbert-Transformation  um 90 Grad phasenverschoben. In der Vergangenheit war es äußerst schwierig, eine Hilbert-Transformation zu erstellen. Heutzutage können DSP-Techniken verwendet werden.

## Hartley SSB Modulator Discrete Tone
### Simulation:

##### Abbildung 1:
![WhatsApp Bild 2024-04-09 um 22 45 12_cee321ca](https://github.com/sofia20K/ksn/assets/165880295/3f8b4fc3-6ad6-485e-8d9c-b02b121785b0)

##### Abbildung 2:

![image](https://github.com/sofia20K/ksn/assets/165880295/da08dec9-7282-4164-9b1a-ec6223e68459)

##### Abbildung 3:

![image](https://github.com/sofia20K/ksn/assets/165880295/74130211-3aef-4216-8ce5-e8812d2cf12e)



Abbildung 1 zeigt einen Phasing-Modulator, der auf GNU Radio basiert. Die Signalquelle ist ein diskreter Ton, der zwischen 300Hz und 2700Hz variieren kann. Der Träger wird der Einfachheit halber mit 10 KHz gewählt. Der USB wird durch Addition der beiden I- und Q-Zweige bestimmt, der LSB durch Subtraktion des Q-Zweigs. Abbildung 2 zeigt die 90-Grad-Phasenverschiebung zwischen den I- und Q-Informationssignalen. Abbildung 3 zeigt das Ausgangsspektrum mit dem USB. Die Unterdrückung des LSB ist am besten bei 1300Hz >60dB. Die Unterdrückung nimmt bei niedrigeren Audiofrequenzen ab.

## Hartley SSB Modulator 300-2700 Hz Voice

Abbildung 4 zeigt einen ähnlichen GNU-Radio-Modulator wie in Abbildung 1, nur dass diesmal die Informationsquelle ein Audio-Quellblock ist. Dieser nimmt den Ton des Laptops auf und ist auf 300-2700 Hz bandgefiltert. Abbildung 5 zeigt die I- und Q-Informationssignale und Abbildung 6 zeigt das SSB-USB-Ausgangsspektrum.

##### Abbildung 4:

![image](https://github.com/sofia20K/ksn/assets/165880295/51f0d956-b3c6-4cb2-af5b-473d9c970147)


##### Abbildung 5:

![image](https://github.com/sofia20K/ksn/assets/165880295/01d4a217-81a8-4700-84a5-3ad423e3393e)


##### Abbildung 6:

![image](https://github.com/sofia20K/ksn/assets/165880295/f1f73122-40d2-4bdd-a284-0ab576f8e5ad)








