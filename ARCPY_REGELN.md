# ArcPy Kritische Regeln — FaSi ZH
# Aus realen Bugs dieser Projekte destilliert

## RULE 1: Cursor IMMER mit with-Statement
```python
with arcpy.da.SearchCursor(fc, fields) as cursor:
    for row in cursor:
        ...
# NIEMALS: cursor = arcpy.da.SearchCursor(...) ohne with
```

## RULE 2: Module-Cache vor jedem Run löschen (ArcGIS Pro!)
```python
import sys
for mod in list(sys.modules.keys()):
    if "nsm" in mod or "wirkung" in mod or mod == "config":
        del sys.modules[mod]
sys.path.insert(0, r"C:\PROJEKTPFAD")
import config
print("START_AB_SCHRITT:", config.START_AB_SCHRITT)
# ERST wenn Wert korrekt → Runner starten!
```

## RULE 3: Kein trailing backslash in Pfad-Strings
```python
BASISPFAD = r"C:\tmp_fasi\NSM"    # ✅ korrekt
BASISPFAD = r"C:\tmp_fasi\NSM\"   # ❌ ImportError!
```

## RULE 4: SDE-Export Filter Wirkungskontrolle
```python
WHERE = "AKTUELLES_DOSSIER_STATUS IN \
    ('PROJ 3 Projektabrechnung', 'PROJ 4 Projekt abgeschlossen')"
# PROJ 1/2 AUSSCHLIESSEN (SOLLM-Daten noch geplant, nicht effektiv)
```

## RULE 5: Koordinatensystem IMMER explizit setzen
```python
SR = arcpy.SpatialReference(2056)  # CH1903+/LV95
```

## RULE 6: in_memory nach Gebrauch löschen
```python
arcpy.management.Delete("in_memory/temp_fc")
```

## RULE 7: Netzpfade mit normpath
```python
pfad = os.path.normpath(r"\\home.kt.ktzh.ch\B289SS2$\...")
```

## RULE 8: Feldnamen SDE → GDB Mapping (Wirkungskontrolle)
| SDE | GDB |
|-----|-----|
| PROJEKTGUID | PROJEKTGUI |
| AKTUELLES_DOSSIER_SOLL_M5 | SOLLM5 |
| AKTUELLES_DOSSIER_SOLL_M6 | SOLLM6 |

## RULE 9: ArcGIS Pro nach Toolbox-Edit → komplett neu starten

## RULE 10: ApplySymbologyFromLayer — explizites Feld-Mapping
```python
arcpy.management.ApplySymbologyFromLayer(
    in_layer=lyr,
    in_symbology_layer=r"C:\...\Symbol.lyrx",
    symbology_fields=[["VALUE_FIELD", "FELD_AUS_LYRX", "FELD_IN_LAYER"]],
    update_symbology="MAINTAIN"
)
# NIEMALS "#" als Platzhalter — immer explizit angeben!
```
