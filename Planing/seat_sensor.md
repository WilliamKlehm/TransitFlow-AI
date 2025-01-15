
# Projektplan: Sitzsensoren-Anwendung

## Ziel
Simuliere Daten, die die Belegung der Sitzplätze in einem Straßenbahnabschnitt erfassen, und sende diese Daten an das Kafka-Topic `seat_sensor_data`.

## Tasks

### 1. Projektinitialisierung
- Erstelle ein neues C#-Projekt (`SeatSensorApp`).
- Installiere das Kafka-Producer-Paket (`Confluent.Kafka`).

### 2. Definition der Datenstruktur
- Erstelle eine Klasse `SeatSensorData` mit folgenden Feldern:
  - `timestamp`: Zeitstempel des Ereignisses.
  - `line_id`: ID der Straßenbahnlinie.
  - `train_id`: ID des Zuges.
  - `section`: Bereich des Zuges (z. B. "front", "middle", "rear").
  - `total_seats`: Gesamte Sitzplatzanzahl.
  - `occupied_seats`: Anzahl der belegten Sitzplätze.

### 3. Kafka-Producer-Setup
- Konfiguriere den Kafka-Producer:
  - Bootstrap-Server: `localhost:9092`.
  - Topic: `seat_sensor_data`.

### 4. Daten-Simulation
- Implementiere eine Funktion, die zufällige Daten für Sitzsensoren generiert:
  - Simuliere unterschiedliche Bereiche des Zuges (z. B. 3 Abschnitte).
  - Generiere zufällige Belegungswerte (0–100%).
  - Aktualisiere den Zeitstempel.

### 5. Daten senden
- Sende die generierten Daten im JSON-Format an das Kafka-Topic.
- Frequenz: Alle 1 Minute.

### 6. Logging
- Protokolliere gesendete Daten für jeden Abschnitt.
