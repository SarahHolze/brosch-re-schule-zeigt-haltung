# Workflow: Zusammenarbeit mit Claude

Diese Dokumentation beschreibt den etablierten Workflow für die Zusammenarbeit mit Claude bei der Bearbeitung von Texten in diesem Repository.

## Kontext

Da alle Änderungen über einen GitHub-Account (SarahHolze) laufen, ist der klassische Review-Prozess mit Approval nicht möglich. Deshalb haben wir einen angepassten Workflow entwickelt.

## Workflow-Schritte

### 1. Änderungswunsch äußern

**Du (Sarah):** Beschreibst, welche Änderungen am Text vorgenommen werden sollen.

**Beispiel:**
> "Überarbeite den Artikel sprachlich. Vermeide Substantivierungen und mache ihn leichter verständlich."

### 2. Entwurf erstellen

**Claude:** 
- Erstellt einen **neuen Branch** (z.B. `sprachliche-ueberarbeitung`)
- Nimmt die gewünschten Änderungen vor
- Erstellt einen **Pull Request**

### 3. Review durch Zeilennummern

**Du (Sarah):** Schaust dir den PR auf GitHub an (Tab "Files changed") und gibst Feedback anhand der Zeilennummern im Diff:

**Beispiel:**
```
3: annehmen
5: ablehnen
7: ablehnen
9: alles annehmen außer den ersten Satz
```

**Bedeutung:**
- ✅ **annehmen** = Änderung übernehmen
- ❌ **ablehnen** = Original beibehalten
- 🔄 **ändern in: ...** = Alternative Formulierung gewünscht

### 4. Finale Änderungen committen

**Claude:**
- Commitet **nur die akzeptierten Änderungen direkt auf main**
- Schließt den Review-PR
- Ergebnis: Saubere Historie mit nur akzeptierten Änderungen

## Vorteile dieses Workflows

✅ **Visuelle Nachvollziehbarkeit:** Alle vorgeschlagenen Änderungen sind im PR-Diff sichtbar (rot/grün)

✅ **Volle Kontrolle:** Du entscheidest bei jeder Zeile einzeln

✅ **Saubere Historie:** Auf main landen nur akzeptierte Änderungen

✅ **Einfache Kommunikation:** Zeilennummern statt langer Textbeschreibungen

## Technische Details

### Branch-Strategie
- `main` = produktive Version, enthält nur finale Änderungen
- Feature-Branches (z.B. `sprachliche-ueberarbeitung`) = Vorschläge zur Review
- Review-Branches werden nach Commit auf main nicht gemergt, sondern geschlossen

### Commit-Messages
Aussagekräftige Commit-Messages beschreiben die vorgenommenen Änderungen:

**Beispiel:**
```
Sprachliche Anpassungen: Einleitung und Abschnitt "Das Problem" überarbeitet
```

### Pull Requests
Pull Requests dienen als Visualisierungs-Tool für Änderungen, nicht als Merge-Vehikel.

## Beispiel-Ablauf

1. **Du:** "Überarbeite Kapitel X sprachlich"
2. **Claude:** Erstellt Branch `kapitel-x-ueberarbeitung` + PR
3. **Du:** Schaust PR an → "Zeile 3: annehmen, Zeile 7: ablehnen"
4. **Claude:** Commitet akzeptierte Änderungen direkt auf main, schließt PR
5. **Ergebnis:** Kapitel X ist auf main aktualisiert ✅

## Wichtige Prinzipien

🎯 **Immer neue Branches für neue Änderungsrunden**

🎯 **Pull Requests als Vorschau, nicht zum Mergen**

🎯 **Finale Änderungen direkt auf main**

🎯 **Kommunikation über Zeilennummern aus dem Diff**

---

*Dokumentiert am: 22. Januar 2026*  
*Repository: broschüre-schule-zeigt-haltung*  
*Workflow etabliert für: Kollaboratives Texten mit Claude*