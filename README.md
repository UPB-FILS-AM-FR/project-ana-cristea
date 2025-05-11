
# Moniteur de Santé avec Détection de Chute

## Auteur
**[Votre Nom Complet]**

## Description
Ce projet consiste en un dispositif portable de surveillance de la santé capable de mesurer le rythme cardiaque, le niveau d'oxygène dans le sang (SpO₂), la température corporelle et de détecter les chutes brusques. Les données sont affichées sur un écran OLED, et une alerte sonore est émise en cas d'anomalie (rythme cardiaque anormal, chute détectée).

## Motivation
Ce dispositif vise à fournir une surveillance en temps réel de l'état de santé de l'utilisateur, particulièrement utile pour les personnes âgées, les patients souffrant de troubles cardiovasculaires ou les sportifs. La détection rapide d'une chute peut être cruciale pour prévenir des complications graves. Ce projet s'inscrit dans le contexte du développement des dispositifs médicaux portables connectés (IoT).

## Architecture

- **ESP32** – Microcontrôleur principal gérant toutes les composantes.
- **MAX30102** – Capteur de rythme cardiaque et SpO₂, communication via I2C.
- **DS18B20** – Capteur de température corporelle, communication via OneWire.
- **MPU6050** – Accéléromètre et gyroscope pour détecter les mouvements brusques.
- **OLED SSD1306** – Affichage des valeurs mesurées.
- **Buzzer actif** – Alerte sonore en cas d'incident.
- **Batterie LiPo 3.7V + TP4056** – Alimentation mobile rechargeable.

## Diagramme en Blocs

```
[ MAX30102 ]       [ DS18B20 ]        [ MPU6050 ]
      |                  |                  |
      +--------+---------+--------+---------+
               |                  |
            [   ESP32 (Microcontrôleur)   ]
               |                  |
        [ OLED SSD1306 ]     [ Buzzer ]
               |
         [ Batterie + TP4056 ]
```

## Schéma Électrique

Le schéma électrique détaillé du projet est disponible dans le répertoire du projet sous le nom `schematic.png`. Ce schéma illustre les connexions entre les composants suivants :

- **ESP32**
- **MAX30102**
- **DS18B20**
- **MPU6050**
- **OLED SSD1306**
- **Buzzer actif**
- **TP4056**
- **Batterie LiPo 3.7V**

## Composants

| Composant           | Utilisation                         | Prix (approx.) |
|---------------------|-------------------------------------|----------------|
| ESP32               | Microcontrôleur principal           | 40 RON         |
| MAX30102            | Capteur de rythme cardiaque et SpO₂ | 30 RON         |
| DS18B20             | Capteur de température              | 10 RON         |
| MPU6050             | Accéléromètre et gyroscope          | 20 RON         |
| OLED SSD1306        | Affichage des données               | 25 RON         |
| TP4056              | Module de charge pour batterie      | 7 RON          |
| Batterie LiPo 3.7V  | Alimentation du système             | 25 RON         |
| Buzzer actif        | Alerte sonore                       | 5 RON          |
| Breadboard          | Plaque de prototypage               | 10 RON         |
| Fils de connexion   | Connexions entre composants         | 7 RON          |
| **Total**           |                                     | **179 RON**    |

## Bibliothèques Utilisées

| Bibliothèque            | Description                                      | Utilisation                            |
|-------------------------|--------------------------------------------------|----------------------------------------|
| Wire.h                  | Communication I2C standard                       | Pour MAX30102, MPU6050, OLED           |
| Adafruit_GFX            | Bibliothèque graphique de base                   | Contrôle de l'affichage OLED           |
| Adafruit_SSD1306        | Pilote pour écran OLED SSD1306                   | Affichage des données                  |
| OneWire                 | Protocole de communication OneWire               | Communication avec DS18B20             |
| DallasTemperature       | Support pour le capteur DS18B20                  | Lecture de la température              |
| SparkFun MAX3010x       | Pilote pour le capteur MAX30102                  | Mesure du rythme cardiaque et SpO₂     |
| MPU6050.h               | Bibliothèque pour le capteur MPU6050             | Détection des mouvements brusques      |

## Journal de Bord

| Semaine               | Activités réalisées                                 |
|-----------------------|-----------------------------------------------------|
| Semaine 6 - 12 Mai    | Choix du sujet, acquisition des composants, schéma  |
| Semaine 7 - 19 Mai    | Tests individuels des capteurs (pouls, température, chute) |
| Semaine 8 - 26 Mai    | Intégration du système, alerte sonore, documentation finale |

## Liens de Référence

- [Tutoriel Random Nerd - MAX30102 avec ESP32](https://randomnerdtutorials.com/esp32-max30102-heart-rate-oximeter-spo2/)
- [Circuit Digest - Détection de chute avec MPU6050](https://circuitdigest.com/microcontroller-projects/fall-detection-system-using-arduino-and-mpu6050)
- [Adafruit - Écran OLED SSD1306](https://learn.adafruit.com/monochrome-oled-breakouts/overview)
- [Conseils d'alimentation pour ESP32](https://randomnerdtutorials.com/esp32-battery-power/)
