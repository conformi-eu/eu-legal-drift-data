# EU Legal Drift Data

**Machine-readable weekly intelligence on changes to EU secondary law.**
Maschinenlesbare Wochen-Intelligenz zu Änderungen im EU-Sekundärrecht.
Données hebdomadaires lisibles par machine sur l'évolution du droit dérivé de l'UE.

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

---

## 🇬🇧 What this is

A weekly, frozen count of **EU secondary-law acts** (EUR-Lex CELLAR sector 3:
regulations, directives, decisions, recommendations) that **entered into force**
in a given ISO calendar week — and how many of them **amend existing legal acts**.

- **Frozen:** Once a calendar week is published, its numbers never change.
- **Verifiable:** Every figure is traceable to individual CELEX identifiers.
- **Conservative:** Consolidated versions (sector 0) and soft law (sector 5) are
  deliberately excluded to avoid double-counting and over-claiming.
- **Source of truth:** EUR-Lex CELLAR (publications.europa.eu).

### Files
- [`data/latest.json`](data/latest.json) — the most recent completed week
- [`data/history.json`](data/history.json) — aggregate figures for all published weeks (append-only)
- `data/{ISO-week}.json` — full per-week archive (e.g. `data/2026-W20.json`)

### How to cite (current release — 2026-W20, 2026-05-11 → 2026-05-17)

> EU Legal Drift Monitor (2026-W20): 35 new EU secondary-law acts entered into force (21 Regulations, 14 Decisions). 17 of which amend existing legal acts. Source: Conformi, EUR-Lex CELLAR sector 3.

---

## 🇩🇪 Worum es geht

Eine wöchentliche, eingefrorene Zählung von **EU-Sekundärrechtsakten**
(EUR-Lex CELLAR Sektor 3: Verordnungen, Richtlinien, Beschlüsse, Empfehlungen),
die in einer bestimmten ISO-Kalenderwoche **in Kraft getreten** sind — und wie
viele davon **bestehende Rechtsakte ändern**.

- **Eingefroren:** Einmal veröffentlichte Wochenzahlen ändern sich nie.
- **Nachprüfbar:** Jede Zahl ist auf einzelne CELEX-Nummern rückführbar.
- **Konservativ:** Konsolidierte Fassungen (Sektor 0) und Soft Law (Sektor 5)
  sind bewusst ausgeschlossen.
- **Quelle:** EUR-Lex CELLAR (publications.europa.eu).

### Zitierweise (aktuelles Release — 2026-W20, 2026-05-11 → 2026-05-17)

> EU Legal Drift Monitor (2026-W20): 35 neue EU-Sekundärrechtsakte in Kraft getreten (21 Verordnung, 14 Beschluss). 17 davon ändern bestehende Rechtsakte. Quelle: Conformi, EUR-Lex CELLAR Sektor 3.

---

## 🇫🇷 De quoi s'agit-il

Un décompte hebdomadaire et figé des **actes de droit dérivé de l'UE**
(EUR-Lex CELLAR secteur 3 : règlements, directives, décisions, recommandations)
**entrés en vigueur** au cours d'une semaine calendaire ISO donnée — et combien
d'entre eux **modifient des actes juridiques existants**.

- **Figé :** Une fois publiés, les chiffres d'une semaine ne changent jamais.
- **Vérifiable :** Chaque chiffre est traçable jusqu'aux identifiants CELEX.
- **Conservateur :** Les versions consolidées (secteur 0) et le droit souple
  (secteur 5) sont délibérément exclus.
- **Source :** EUR-Lex CELLAR (publications.europa.eu).

### Comment citer (version actuelle — 2026-W20, 2026-05-11 → 2026-05-17)

> EU Legal Drift Monitor (2026-W20): 35 nouveaux actes de droit dérivé de l'UE entrés en vigueur (21 Règlements, 14 Décisions). 17 d'entre eux modifient des actes juridiques existants. Source : Conformi, EUR-Lex CELLAR secteur 3.

---

## Methodology / Methodik / Méthodologie

EUR-Lex CELLAR sector 3 (EU secondary law: regulations, directives, decisions, recommendations). Counts acts with entry into force (entry_into_force) within the calendar-week interval (Mon 00:00 – Sun 23:59 UTC). 'Amends existing' = act references an existing legal act via AMENDS. Consolidated versions (sector 0) and soft law (sector 5) are deliberately excluded.

**DE:** EUR-Lex CELLAR Sektor 3 (EU-Sekundärrecht: Verordnungen, Richtlinien, Beschlüsse, Empfehlungen). Erfasst Rechtsakte mit Inkrafttreten (entry_into_force) im Kalenderwochen-Intervall (Mo 00:00 – So 23:59 UTC). 'Ändert Bestehendes' = Akt referenziert via AMENDS einen bestehenden Rechtsakt. Konsolidierte Fassungen (Sektor 0) und Soft Law (Sektor 5) sind bewusst ausgeschlossen.

**FR:** EUR-Lex CELLAR secteur 3 (droit dérivé de l'UE : règlements, directives, décisions, recommandations). Comptabilise les actes entrés en vigueur (entry_into_force) dans l'intervalle de la semaine calendaire (lun. 00:00 – dim. 23:59 UTC). « Modifie l'existant » = l'acte référence un acte juridique existant via AMENDS. Les versions consolidées (secteur 0) et le droit souple (secteur 5) sont délibérément exclus.

---

## Schema

`data/latest.json` follows schema `conformi-eu-legal-drift/1`:

```json
{
  "week_id": "2026-W20",
  "period_start": "2026-05-11",   // Monday, UTC
  "period_end": "2026-05-17",     // Sunday, UTC
  "new_acts_total": 35,
  "by_type_code": { "R": <regulations>, "L": <directives>, "D": <decisions>, "H": <recommendations> },
  "amending_existing_total": 17,
  "acts": [ { "celex": "...", "type": "R", "entry_into_force": "...", "amends": ["<CELEX>", ...] } ],
  "citation": { "de": "...", "en": "...", "fr": "..." },
  "methodology": { "de": "...", "en": "...", "fr": "..." },
  "license": "CC BY 4.0",
  "data_as_of": "...",
  "source": "EUR-Lex CELLAR SPARQL (publications.europa.eu)"
}
```

`by_type_code` is language-neutral and stable for machine parsing.
Human-readable labels are provided per language under `by_type` and `acts[].type_label`.

---

## License

This dataset is published under [Creative Commons Attribution 4.0 International
(CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
You are free to share and adapt, including for commercial use, **with attribution**:

> Source: Conformi — EU Legal Drift Monitor (https://conformi.eu)

Underlying legal acts are sourced from EUR-Lex CELLAR (© European Union,
https://eur-lex.europa.eu), reused under the EUR-Lex reuse policy.

---

*Maintained by [Conformi](https://conformi.eu) · EU legal research with verifiable sources.*
