You will find the English ReadMe at the end of the document.

# SCD30 CO₂-, Temperatur- & Luftfeuchtigkeitssensor MakeCode-Erweiterung für den Calliope mini

Diese MakeCode-Erweiterung ermöglicht die Ansteuerung des **Sensirion SCD30** CO₂-Sensors mit dem **Calliope mini**. Sie erlaubt die Messung von **CO₂ (ppm)**, **Temperatur (°C)** und **Luftfeuchtigkeit (%)** über den Grove A0 Anschluss (I²C).

---

## 🔧 Installation

So fügst du die Erweiterung deinem MakeCode-Projekt hinzu:

1. Öffne [makecode.calliope.cc](https://makecode.calliope.cc/)
2. Erstelle ein neues Projekt
3. Klicke oben rechts auf das Zahnrad ⚙️ → **Erweiterungen**
4. Füge folgende GitHub-URL ein:  
   `https://github.com/calliope-edu/pxt-SCD30`  
5. In der Blockpalette erscheint nun die neue Kategorie **SCD30**.

---

## 📦 Funktionen

Die Erweiterung stellt folgende Blöcke in der Kategorie **SCD30** zur Verfügung:

- `CO2 value`: Gibt die aktuelle CO₂-Konzentration in ppm zurück  
- `Temperature`: Gibt die aktuelle Temperatur in °C zurück  
- `Humidity`: Gibt die aktuelle relative Luftfeuchtigkeit in % zurück  
- `Calibrate sensor to 400 ppm`: Kalibriert den Sensor auf 400 ppm (in der Regel nach ca. 10 Minuten Frischluftzufuhr)

---

## 🧪 Beispiel

```blocks
basic.forever(function () {
    basic.showNumber(SCD30.CO2_value())
    basic.pause(2000)
})
```
Dieses Beispiel zeigt alle 2 Sekunden den aktuellen CO₂-Wert auf dem LED-Display an.

## 🔌 Hardware-Anschluss
* Schnittstelle: I²C
* Empfohlener Anschluss: Grove A0 auf dem Calliope mini

## ℹ️ Technische Details

Der Sensor misst:

CO₂-Konzentration von 0 bis 10.000 ppm
Temperatur in Grad Celsius (°C)
Relative Luftfeuchtigkeit in Prozent (%)
Der Kalibrierungsblock setzt den CO₂-Wert auf eine Basis von 400 ppm, was dem typischen Frischluftwert entspricht.

Intern wird der Sensor etwa alle 2 Sekunden im Hintergrund über I²C abgefragt.

## 🎓 Praxisbeispiel: CO₂-Ampel

Baue mit einem RGB-NeoPixel-Ring eine einfache CO₂-Ampel zur Anzeige der Luftqualität:

Grün: CO₂ < 800 ppm
Gelb: CO₂ zwischen ca. 800–1.200 ppm
Rot: CO₂ > 1.200 ppm
Verwende dazu zusätzlich die Neopixel-Erweiterung und verknüpfe den CO₂-Wert mit Farbe oder Anzahl der LEDs.




# SCD30 CO₂, Temperature & Humidity Sensor MakeCode-Extension for Calliope mini

This MakeCode extension adds support for the **Sensirion SCD30** CO₂ sensor on the **Calliope mini**, enabling measurements of **CO₂ (ppm)**, **temperature (°C)**, and **humidity (%)** via Grove A0 (I²C).

---

## 🔧 Installation

Add the extension to your MakeCode project:

1. Go to [makecode.calliope.cc](https://makecode.calliope.cc/)
2. Create a new project
3. Click the gear icon ⚙️ in the top-right → **Extensions**
4. Paste the following GitHub URL:  
   `https://github.com/calliope-edu/pxt-SCD30`  
5. You’ll now see a new category named **SCD30** in the block palette :contentReference[oaicite:1]{index=1}

---

## 📦 Features

The extension provides the following blocks under the **SCD30** category:

- `CO2 value`: Returns the current CO₂ concentration in ppm  
- `Temperature`: Returns the current temperature in °C  
- `Humidity`: Returns the current relative humidity in %  
- `Calibrate sensor to 400 ppm`: Calibrates the sensor (typically done in fresh air after ~10 min) :contentReference[oaicite:2]{index=2}

---

## 🧪 Example Usage

```blocks
basic.forever(function () {
    basic.showNumber(SCD30.CO2_value())
    basic.pause(2000)
})
```

## 🔌 Hardware Connections

Interface: I²C (connected via Grove or directly via SDA/SCL)
Connector: Usually Grove A0 on Calliope mini 

## ℹ️ Technical Details

Measures:
CO₂ concentration from 0 to 10,000 ppm
Temperature in °C
Relative humidity in %
The calibration block sets 400 ppm baseline, typical of fresh outdoor air 

Internally, the extension uses a background loop polling the sensor via I²C every ~2 seconds

## 🎓 Practical Example

You can build a simple CO₂ traffic light with an RGB NeoPixel ring indicating air quality levels:

Green: CO₂ < 800 ppm
Yellow: CO₂ between ~800–1,200 ppm
Red: CO₂ > 1,200 ppm
Use the Neopixel extension in addition to SCD30 and map the CO₂ value to LED count or color.



## Supported target

* PXT/calliopemini



## License

MIT
