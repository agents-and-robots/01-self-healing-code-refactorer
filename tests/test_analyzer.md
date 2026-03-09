# Test: Analyzer

## Natürliche Sprache
Der Analyzer soll mindestens einen Syntaxfehler erkennen, wenn der Code syntaktisch ungültig ist.

## Maschinenlesbare Struktur
input:
  code: "def broken(:\n  pass"

expected:
  issues:
    - type: "syntax_error"

