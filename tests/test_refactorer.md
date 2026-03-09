# Test: Refactorer

## Natürliche Sprache
Der Refactorer soll offensichtliche Syntaxfehler korrigieren und eine gültige Funktionsdefinition erzeugen.

## Maschinenlesbare Struktur
input:
  code: "def broken(:\n  pass"
  issues:
    - type: "syntax_error"

expected_contains:
  "def broken():"

