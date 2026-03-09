# Self-Healing Code Refactorer

Ein autonomer Refactoring-Agent, der fehlerhaften oder schlecht strukturierten Python-Code analysiert, gegen definierte Constraints prüft und selbstständig korrigiert.  
Dieses Projekt demonstriert die Grundlagen des Prompt-Driven Developments (PDD): Feedback-Loops, Validierung, Constraints und iterative Selbstkorrektur.

## Ziel des Projekts

Der Self-Healing Code Refactorer soll:

- fehlerhaften Python-Code einlesen
- strukturelle und syntaktische Probleme erkennen
- gegen definierte Regeln (PEP8, Sicherheitschecks, Stilrichtlinien) prüfen
- selbstständig Korrekturen vornehmen
- die Korrekturen erneut validieren (Feedback-Loop)

## Hardware Requirements

Dieses Projekt ist vollständig lokal ausführbar und benötigt keine spezielle Hardware.
Siehe `hardware-requirements.md` für Details.

## Projektstruktur

/src  
    analyzer.py  
    refactorer.py  
    validator.py  

/tests  
    test_analyzer.md  
    test_refactorer.md  
    test_validator.md  

/docs  
    architecture.md  

instructions.md  
README.md  
credits.md  

## Lizenz

Dieses Projekt steht unter der MIT License (siehe unten).

## Credits

Siehe `credits.md`.

