# Drum Sampler: From Scratch

Dieses Repository enthält ein einfaches Python-Skript, das Drum-Samples aus einem Ordner per MIDI-Datei ansteuert und daraus eine WAV-Datei rendert – ganz ohne Plugins, JACK, ALSA oder sonstigen Audio-Overhead.

## Voraussetzungen
- Python 3
- Module: `mido`, `soundfile`, `numpy`
  
Installiere die Module (empfohlen in einer venv):
```bash
python3 -m venv venv
source venv/bin/activate
pip install mido soundfile numpy
```
Oder systemweit (z.B. auf Ubuntu):
```bash
sudo apt install python3-mido python3-soundfile python3-numpy
```

## Dateien
- `script` – Das Hauptskript
- `../2 Funk Kit Samples/` – Ordner mit Drum-Samples (WAV)
- `../funky_drum_pattern.mid` – Beispiel-MIDI-Drum-Pattern

## Nutzung

### Einzelnes Rendering:
```bash
python3 script ../funky_drum_pattern.mid "../2 Funk Kit Samples/" test_output.wav
```

### Batch-Rendering (jede Kick-Variante):
```bash
python3 script --batch-kick ../funky_drum_pattern.mid "../2 Funk Kit Samples/" test_output
```

Das Skript erzeugt dann für jede Kick-Drum eine eigene WAV-Datei (z.B. `test_output_kick_Kick Funk 1.wav`).

## Hinweise
- Die Zuordnung der Samples zu MIDI-Noten erfolgt automatisch anhand der Dateinamen (siehe Skript).
- Die MIDI-Datei sollte ein Drum-Pattern enthalten, das zu den Samples passt.
- Für eigene Kits einfach den Sample-Ordner austauschen. 