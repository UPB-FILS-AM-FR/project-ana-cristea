# Health Monitor with Fall Detection

## Author
Cristea Ana

---

## Description
Acest proiect este un sistem portabil de monitorizare a sănătății care măsoară pulsul, nivelul de oxigen din sânge, temperatura corporală și detectează căderile bruște. Datele sunt afișate pe un display OLED, iar sistemul poate emite o alertă sonoră în caz de anomalii (puls scăzut/ridicat, cădere).

---

## Motivation
Acest dispozitiv are ca scop monitorizarea stării de sănătate a utilizatorului în timp real, fiind util pentru persoane în vârstă, pacienți cu probleme cardiovasculare sau sportivi. Detectarea rapidă a unei căderi poate fi esențială pentru prevenirea complicațiilor în cazuri critice. Este un proiect relevant în contextul dezvoltării sistemelor de tip wearable medical IoT.

---

## Architecture

- **ESP32** – microcontroller principal, gestionează toate componentele.
- **MAX30102** – senzor puls și SpO₂, comunică pe I2C.
- **DS18B20** – senzor temperatură corporală, comunică pe OneWire.
- **MPU6050** – senzor accelerometru și giroscop, detectează mișcări bruște.
- **OLED SSD1306** – afișează valorile măsurate.
- **Buzzer activ** – oferă alertă sonoră în caz de incident.
- **Baterie LiPo 3.7V + TP4056** – alimentare mobilă și reîncărcabilă.

---

## Block Diagram

```
[ MAX30102 ]       [ DS18B20 ]        [ MPU6050 ]
      |                  |                  |
      +--------+---------+--------+---------+
               |                  |
            [   ESP32 (Microcontroller)   ]
               |                  |
        [ OLED SSD1306 ]     [ Buzzer ]
               |
         [ Battery + TP4056 ]
```

---

## Schematic

![Schematic](A_detailed_digital_illustration_schematic_diagram_.png)

---

## Components

| Device            | Usage                          | Price   |
|-------------------|----------------------------------|---------|
| ESP32             | Microcontroller principal        | 40 RON  |
| MAX30102          | Senzor puls și SpO₂              | 30 RON  |
| DS18B20           | Senzor temperatură               | 10 RON  |
| MPU6050           | Accelerometru și giroscop        | 20 RON  |
| OLED SSD1306      | Afișare valori                   | 25 RON  |
| TP4056            | Încărcare baterie                | 7 RON   |
| Baterie LiPo      | Alimentare                       | 25 RON  |
| Buzzer activ      | Alertă sonoră                    | 5 RON   |
| Breadboard        | Placă prototip                   | 10 RON  |
| Jumper wires      | Conectare componente             | 7 RON   |
| **TOTAL**         |                                  | **179 RON** |

---

## Libraries

| Library            | Description                                   | Usage                                    |
|--------------------|-----------------------------------------------|------------------------------------------|
| Wire.h             | I2C communication (standard)                  | Pentru MAX30102, MPU6050, OLED           |
| Adafruit_GFX       | Graphics core library                         | Control display OLED                     |
| Adafruit_SSD1306   | OLED display driver                           | Afișare date pe ecran                    |
| OneWire            | OneWire communication protocol                | Comunicare cu DS18B20                    |
| DallasTemperature  | Suport pentru senzorul DS18B20                | Citirea temperaturii                     |
| SparkFun MAX3010x  | Driver pentru senzorul de puls MAX30102       | Puls și SpO₂                             |
| MPU6050.h          | Librărie pentru accelerometru MPU6050         | Detectarea căderilor                     |

---

## Log

| Săptămâna         | Activități desfășurate                     |
|-------------------|--------------------------------------------|
| Week 6 - 12 May   | Alegerea temei, achiziționare componente, schema |
| Week 7 - 19 May   | Testare senzori individual (puls, temp, cădere) |
| Week 8 - 26 May   | Integrare sistem, alertă buzzer, documentație finală |

---

## Reference Links

- [Tutorial: Using MAX30102 with ESP32 (Random Nerd)](https://randomnerdtutorials.com/esp32-max30102-heart-rate-oximeter/)
- [MPU6050 Fall Detection Example](https://circuitdigest.com/microcontroller-projects/fall-detection-system-using-arduino-and-mpu6050)
- [Adafruit OLED SSD1306](https://learn.adafruit.com/monochrome-oled-breakouts/arduino-library-and-examples)
- [ESP32 Power Supply Tips](https://randomnerdtutorials.com/esp32-battery-power/)