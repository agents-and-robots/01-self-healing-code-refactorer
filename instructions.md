# LLM Instructions – Self-Healing Code Refactorer

Diese Datei definiert alles, was ein LLM benötigt, um dieses Projekt vollständig selbständig umzusetzen:
- Input/Output-Protokoll
- Orchestrator-Logik
- Regelwerk / Constraints
- Aufgabenbeschreibung
- How-To-Use für Code-Assistenten

---

## 1. Ziel

Erstelle ein System, das fehlerhaften Python-Code analysiert, refaktoriert, validiert und in einem Feedback-Loop verbessert, bis der Code gültig ist.

---

## 2. Input/Output-Protokoll

### Gesamtinput:
- code: string

### Gesamtoutput:
- analysis: dict
- refactored_code: string
- validation: dict
- iterations: int

### Endbedingung:
- validation.valid == true  
oder  
- iterations >= 5

---

## 3. Modul-Spezifikationen

### Analyzer (/src/analyzer.py)

Signatur: analyze(code: str) -> dict  
Rückgabeformat:

- issues: Liste von Objekten mit:
  - type: string (syntax_error, style_violation, security_issue, complexity_issue)
  - message: string

### Validator (/src/validator.py)

Signatur: validate(code: str) -> dict  
Rückgabeformat:

- valid: bool
- errors: Liste von Objekten wie oben

### Refactorer (/src/refactorer.py)

Signatur: refactor(code: str, issues: list) -> str  
Rückgabe: syntaktisch gültiger Python-Code

---

## 4. Orchestrator-Logik

1. analysis = analyze(code)
2. issues = analysis.issues
3. refactored_code = refactor(code, issues)
4. validation = validate(refactored_code)
5. Wenn validation.valid == false:
   - code = refactored_code
   - zurück zu Schritt 1
6. Wenn validation.valid == true:
   - Ergebnis zurückgeben

---

## 5. Regelwerk / Constraints

### Syntax
- Python 3.10 kompatibel
- keine Syntaxfehler

### Stil
- max. 88 Zeichen pro Zeile
- snake_case für Funktionen
- CamelCase für Klassen
- sinnvolle Namen
- keine unbenutzten Variablen

### Sicherheit
- kein eval
- kein exec
- keine SQL-Konkatenation
- keine unvalidierten system-Aufrufe

### Komplexität
- Funktionen ≤ 20 Zeilen (soft)
- max. 3 Verschachtelungsebenen

---

## 6. Aufgaben an das LLM

Das LLM soll:

1. analyzer.py implementieren  
2. validator.py implementieren  
3. refactorer.py implementieren  
4. architecture.md ergänzen  
5. Tests in /tests aktualisieren  
6. Optional orchestrator.py implementieren

---

## 7. How-To-Use (für Code-Assistenten)

1. Öffne dieses Repository.  
2. Öffne die Datei `instructions.md`.  
3. Markiere den gesamten Inhalt.  
4. Sende ihn an deinen Code-Assistenten mit der Anweisung:

„Lies diese instructions.md vollständig. Implementiere dann alle beschriebenen Module und Dateien. Halte dich strikt an das Input/Output-Protokoll, das Regelwerk und die Testspezifikation. Beginne mit analyzer.py.“

Damit kann ein LLM das Projekt vollständig autonom umsetzen.

