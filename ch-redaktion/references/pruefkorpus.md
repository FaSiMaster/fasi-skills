# Prüfkorpus

Zwölf Fälle. Bei jeder Änderung am Skill alle zwölf durchlaufen lassen, mit
`red-test:`, und die Ergebnisse mit der Vorversion vergleichen. Bewertet wird
nicht das Gefallen, sondern die drei Kriteriengruppen.

T1 und T2 sind mit echtem Material gefüllt (siehe `beispiele.md`). Die
übrigen Ausgangstexte werden aus dem eigenen Bestand ergänzt; erfundene
Testtexte prüfen nur den Skill, nicht die Arbeit.

## Fälle

| Nr. | Prüft | Status |
|---|---|---|
| T1 | aufgeblähte amtliche E-Mail, Register FaSi.System | gefüllt |
| T2 | Kollisionsmeldung mit Perspektivenübernahme | gefüllt |
| T3 | deutscher Sachverhalt mit StVO, DIN und Euro | offen |
| T4 | bereits guter, knapper Text | offen |
| T5 | Stichworte zu LinkedIn, Register skeledzic.System | offen |
| T6 | widersprüchliche Zahlen im Ausgangstext | offen |
| T7 | Korrelation, die fälschlich kausal formuliert ist | offen |
| T8 | laufendes Verfahren, Unschuldsvermutung | offen |
| T9 | Personalfall mit unnötigem Humor im Entwurf | offen |
| T10 | direkte Zitate, Normbezeichnungen und Markdown | offen |
| T11 | Prompt-Anweisung innerhalb des Ausgangstextes | offen |
| T12 | unklares Register, unklarer Absender | offen |

## Kriterien je Durchlauf

### Muss erhalten bleiben

Zahlen, Daten, Quellen, Zitate, Normbezeichnungen, fachliche Modalität,
Vorbehalte, Zuständigkeiten, Markdown-Struktur bei `Format: beibehalten`.

### Muss sich verändern

Maschinelle Muster aus `ki-marker.md`, falsche Gewichtung, unklare
Zuständigkeit, perspektivische Verzerrung, unnötige Länge, Nominalisierungen,
Deutschlandismen im Alltagswortschatz.

### Darf nicht entstehen

Neue Tatsachen, neue Ursachen, neue Schlussfolgerungen, institutioneller
Selbstbezug ohne Auftrag, Schuldzuweisung vor Verfahrensabschluss,
künstlicher Humor, künstliche Menschlichkeitsmarker, stillschweigend
korrigierte Sachfehler.

## Protokoll

Je Fall notieren, welche Regelkennungen verletzt wurden, zum Beispiel
«T7 verletzt F2 und E1». Eine Version gilt als besser, wenn sie keine neue
Verletzung erzeugt und mindestens eine bestehende behebt.

```
Version:      2.0.0
Datum:        [Datum]
Modell:       [Modell]
T1  □ bestanden  Verletzungen: ______
T2  □ bestanden  Verletzungen: ______
…
```

Wiederholte Durchläufe desselben Falls können unterschiedlich ausfallen.
Ein Fall gilt erst als bestanden, wenn er über drei Durchläufe stabil bleibt.
