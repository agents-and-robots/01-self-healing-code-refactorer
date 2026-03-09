# Test: Validator

## Natürliche Sprache
Der Validator soll ungültigen Code als invalid markieren.

## Maschinenlesbare Struktur
input:
  code: "def broken(:\n  pass"

expected:
  valid: false

