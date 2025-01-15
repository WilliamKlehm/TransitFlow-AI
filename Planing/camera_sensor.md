
# Projektplan: Kamerabasierte Anwendung

## Ziel
Simuliere Daten, die die Anzahl der stehenden und sitzenden Personen in einem Straßenbahnabschnitt basierend auf kamerabasierten Analysen erfassen, und sende diese Daten an das Kafka-Topic `camera_sensor_data`.

## Tasks

### 1. Projektinitialisierung
- Erstelle ein neues C#-Projekt (`CameraSensorApp`).
- Installiere das Kafka-Producer-Paket (`Confluent.Kafka`).

### 2. Definition der Datenstruktur
- Erstelle eine Klasse `CameraSensorData` mit folgenden Feldern:
  - `timestamp`: Zeitstempel des Ereignisses.
  - `line_id`: ID der Straßenbahnlinie.
  - `train_id`: ID des Zuges.
  - `section`: Bereich des Zuges (z. B. "front", "middle", "rear").
  - `standing`: Anzahl der stehenden Personen.
  - `sitting`: Anzahl der sitzenden Personen.

### 3. Kafka-Producer-Setup
- Konfiguriere den Kafka-Producer:
  - Bootstrap-Server: `localhost:9092`.
  - Topic: `camera_sensor_data`.

### 4. Daten-Simulation
- Implementiere eine Funktion, die zufällige Daten für Kamerasensoren generiert:
  - Simuliere unterschiedliche Bereiche des Zuges (z. B. 3 Abschnitte).
  - Generiere zufällige Werte für `standing` und `sitting` (maximale Kapazität beachten).
  - Aktualisiere den Zeitstempel.

### 5. Daten senden
- Sende die generierten Daten im JSON-Format an das Kafka-Topic.
- Frequenz: Alle 30 Sekunden.

### 6. Logging
- Protokolliere gesendete Daten für jeden Abschnitt.
