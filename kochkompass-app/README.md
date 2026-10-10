# Rezepte hinzufügen

Neue Rezepte stehen in der Datei `rezepte.json`. Die App lädt sie beim Start dazu.

## Aufbau eines Rezepts

```json
{
 "name": "Quark-Haferpfannkuchen",
 "meal": "fruehstueck",
 "protein": "ei",
 "prep": 10,
 "total": 15,
 "servings": 1,
 "devices": ["herd"],
 "tags": ["schnell"],
 "ingredients": ["60 g Haferflocken", "2 Stk. Eier", "125 g Magertopfen"],
 "steps": ["Alles mixen.", "3 Min. pro Seite backen."],
 "tip": "Optionaler Hinweis"
}
```

Mehrere Rezepte stehen in der Liste `recipes`, getrennt durch Kommas. Nach dem letzten Rezept steht kein Komma.

| Feld | Werte |
|---|---|
| `meal` | `fruehstueck`, `haupt`, `snack` |
| `protein` | `huelsen`, `tofu`, `ei`, `milch`, `gefluegel`, `fisch`, `rot` |
| `prep` | Arbeitszeit in Minuten |
| `total` | Gesamtzeit in Minuten |
| `servings` | Portionen, die das Rezept ergibt |
| `devices` | `herd`, `ofen`, `hlf` (Heißluftfritteuse), `mixer` |
| `ingredients` | Menge zuerst: `200 g Rote Linsen`, `1 Stk. Zwiebel`, `2 EL Olivenöl`. Einheiten: g, kg, ml, l, Stk., EL, TL, Zehe |
| `steps` | Ein Eintrag pro Schritt. Steht darin z. B. `20 Min.`, bekommt der Schritt einen Timer |
| `protein_g`, `kcal` | Optional. Nur nötig, wenn Zutaten nicht erkannt werden |

Die Mengen gelten für die Portionen in `servings`. Nährwerte und Einkaufsliste rechnet die App selbst, wenn sie die Zutaten kennt. Die Namen müssen ungefähr stimmen, z. B. `Rote Linsen` oder `Hüttenkäse`. Unbekannte Zutaten stehen trotzdem im Rezept und auf der Einkaufsliste.

## Rezept ändern oder ersetzen

Gib dem Rezept ein Feld `"id": "name-des-rezepts"`. Hat ein Rezept dieselbe `id` wie eines der Startrezepte, ersetzt es dieses.

## Prüfen

Unter „Woche → Einstellungen“ steht, wie viele Rezepte aus `rezepte.json` geladen wurden. Ein Fehler wird dort ebenfalls gemeldet, meist fehlt ein Komma oder eine Klammer.

## Auf GitHub ändern

Öffne `rezepte.json` im Repository, tippe auf das Stift-Symbol, füge das Rezept ein und speichere mit „Commit changes“. Nach ein bis zwei Minuten ist es online. Öffne die App danach zweimal, weil die erste Öffnung noch die alte Version zeigen kann.
