# QA-Checklist — Vor JEDER Code-Ausgabe ausführen

## Python / ArcPy
- [ ] Alle Imports vorhanden und korrekt?
- [ ] Kein trailing backslash in Pfad-Strings?
- [ ] ArcPy Cursor in with-Statement?
- [ ] in_memory nach Gebrauch gelöscht?
- [ ] Koordinatensystem WKID 2056 gesetzt?
- [ ] SDE-Filter korrekt (PROJ 3/4, nicht 1/2)?

## Swiss Norms
- [ ] Raser-Schwelle: SVG Art. 90 speed-dependent (NICHT flat +50)?
- [ ] DWV: Mo–Fr, Feiertage ZH ausgeschlossen?
- [ ] FB 1634 ≠ VSS-Norm korrekt referenziert?
- [ ] Normnummern aus SWISS_NORMS.md geprüft?

## R-Skripte
- [ ] datum als dmy() (nicht as.Date(as.numeric()))?
- [ ] unfallzeit als str_sub() (nicht hm())?
- [ ] Keine duplicate column rename nach clean_names()?
- [ ] furrr-Worker: .data$spalte statt spalte?

## Ausgabe
- [ ] VOLLSTÄNDIGE Datei? Kein Diff, kein «...rest unchanged»?
- [ ] ast.parse() Syntax-Check (Python)?
- [ ] Zahlenformat CH: 1'500 (Apostroph)?
- [ ] Vollständige Datei zum Download (Browser)?
