# Architektur – Self-Healing Code Refactorer

## Module

- analyzer.py – erkennt Probleme im Code
- refactorer.py – erzeugt verbesserten Code
- validator.py – prüft Code gegen ein Regelwerk

## Datenfluss

1. analyze(code)
2. refactor(code, issues)
3. validate(refactored_code)
4. Wiederholen, bis valid = true

