
# Projektplan: Türsensoren-Anwendung

## Ziel
Simuliere Daten, die die Anzahl der ein- und aussteigenden Personen an jeder Haltestelle einer Straßenbahnlinie erfassen, und sende diese Daten an das Kafka-Topic `door_sensor_data`.

## Tasks

### 1. Projektinitialisierung
- Erstelle ein neues C#-Projekt (`DoorSensorApp`).
- Installiere das Kafka-Producer-Paket (`Confluent.Kafka`).

### 2. Definition der Datenstruktur
- Erstelle eine Klasse `DoorSensorData` mit folgenden Feldern:
  - `timestamp`: Zeitstempel des Ereignisses.
  - `line_id`: ID der Straßenbahnlinie.
  - `train_id`: ID des Zuges.
  - `current_stop`: Aktuelle Haltestelle.
  - `boarding`: Anzahl der einsteigenden Personen.
  - `alighting`: Anzahl der aussteigenden Personen.

### 3. Kafka-Producer-Setup
- Konfiguriere den Kafka-Producer:
  - Bootstrap-Server: `localhost:9092`.
  - Topic: `door_sensor_data`.

### 4. Daten-Simulation
- Implementiere eine Funktion, die zufällige Daten für die Türsensoren generiert:
  - Simuliere Haltestellen basierend auf Linienplänen.
  - Generiere zufällige Werte für `boarding` und `alighting` (z. B. 0–20 Personen pro Haltestelle).
  - Aktualisiere den Zeitstempel.

### 5. Daten senden
- Sende die generierten Daten im JSON-Format an das Kafka-Topic.
- Frequenz: Alle 10 Minuten (tagsüber) oder 30 Minuten (nachts).

### 6. Logging
- Implementiere ein einfaches Logging, um gesendete Nachrichten zu protokollieren.
