# Scale Up! Fallstudie „Sell Online“ – Leitfaden für die Vorstellung (SW3/SW4)

Modul Betriebliche Standard-Software (3BSS), HS26, Kleinklasse.
Case: **„Sell Online“ – MyOffice Inc.** (Web Shop, 7 Schritte, `ScaleUp.pdf`)

---

## 0. Was genau verlangt ist (aus euren Unterlagen)

| Vorgabe | Quelle |
|---|---|
| Vorstellung der Scale-Up-Fallstudie in der KK in **SW3 oder SW4** (SW3 = 28.09.–04.10.2026, **Anwesenheitspflicht**) | Semesterprogramm S. 1 + Kap. 5.2.2 |
| Inhalt: **(1) Übersicht zum Case als BPMN, (2) Live-Demonstration in einer Odoo-Instanz, (3) Learnings und Herausforderungen** | Semesterprogramm 5.2.2, Bewertungsraster |
| Zeit: **20 Minuten inkl. 5 Minuten Fragen**, also ca. 15 Minuten Vortrag | Semesterprogramm 5.2.2 |
| **Es werden keine Präsentationsslides benötigt.** Der Fokus liegt auf BPMN und Live-Demo in Odoo. | Folien SW02 KK, Folie „Scale Up!“ |
| Ziel: Die anderen Gruppen sollen einen Eindruck vom Case bekommen und **Tipps** erhalten („Ihr seid die Experten für den Case in der Klasse“) | Folien SW02 KK |
| BPMN erstellen, z. B. mit https://demo.bpmn.io/new oder Camunda | Folien SW02 KK |
| Bewertung: bis **10 Bonuspunkte (= 5 %)** für den Gruppenleistungsnachweis | Semesterprogramm 5.2.2, Bewertungsraster |
| Zuweisung laut Folie: **Gruppe 4 – Web Shop – „Sell Online“** | Folien SW02 KK, „Scale UP – Zuweisung“ |

> Prüft kurz, ob ihr wirklich „Sell Online“ zugeteilt bekommen habt (laut Folie Gruppe 4).
> Alles in diesem Ordner baut auf diesem Case auf.

**Inhalt dieses Ordners**

```
ScaleUp_SellOnline/
├── README.md                                   ← dieser Leitfaden
└── bpmn/
    ├── 01_ScaleUp_SellOnline_Einrichtung.bpmn    ← BPMN 1: der Case (7 Schritte), in demo.bpmn.io öffnen
    ├── 01_ScaleUp_SellOnline_Einrichtung.png/.svg
    ├── 02_ScaleUp_SellOnline_Bestellprozess.bpmn ← BPMN 2: Bestellprozess, den der Shop unterstützt
    └── 02_ScaleUp_SellOnline_Bestellprozess.png/.svg
```

Die `.bpmn`-Dateien könnt ihr auf https://demo.bpmn.io per Drag & Drop öffnen und dort weiter anpassen,
z. B. mit euren Namen in den Lanes.

---

## 1. Ablauf der Präsentation (15 Min. + 5 Min. Fragen)

Roter Faden: **Ausgangslage → Prozess (BPMN) → Umsetzung in Odoo (live) → was wir gelernt haben.**

| Zeit | Teil | Wer (Vorschlag bei 4 Personen) | Inhalt |
|---|---|---|---|
| 0:00–1:30 | Einstieg | Person A | Firma MyOffice Inc. (Büromöbel, lokal bekannt), Ziel des Cases: *Online-Präsenz aufbauen und online verkaufen*. Die 7 Schritte kurz nennen. |
| 1:30–4:30 | BPMN | Person A | BPMN 1 (Einrichtung, 7 Schritte) zeigen, dann BPMN 2 (Bestellprozess Kunde ↔ MyOffice). Die BPMN-Elemente erklären (siehe Kap. 2). |
| 4:30–8:00 | Live-Demo Teil 1 | Person B | Schritte 1–3: Homepage, Produktseite „Office Chair“, SEO |
| 8:00–12:00 | Live-Demo Teil 2 | Person C | Schritte 4–7: Varianten, Cross-Selling (Garantie), Blog, danach **Testkauf** als Kunde |
| 12:00–13:30 | Integration | Person C/D | Zeigen, was der Webshop-Kauf im Backend auslöst: Verkaufsauftrag → Lieferung (Lager) → Rechnung (Buchhaltung). **Ein System, abteilungsübergreifend.** |
| 13:30–15:00 | Learnings & Herausforderungen | Person D | 3–4 konkrete Learnings, Tipps für die anderen Gruppen (siehe Kap. 5) |
| 15:00–20:00 | Fragen | alle | Mögliche Fragen siehe Kap. 6 |

**Bei 3 Personen:** A macht Einstieg + BPMN, B macht Demo Teil 1, C macht Demo Teil 2 + Integration, die Learnings teilt ihr auf (jede Person 1 Learning, gibt ein gutes Bild der Zusammenarbeit).

Tipps zur Form (das zählt im Raster für den GLNW-Vortrag ebenfalls: frei sprechen, Zeit einhalten, jede Person gleich viel Redezeit):

- Ohne Folien reicht **ein Browserfenster mit Tabs** in dieser Reihenfolge:
  1. BPMN 1 (PNG oder demo.bpmn.io)
  2. BPMN 2
  3. Odoo-Backend (eingeloggt als Admin)
  4. Webshop in einem **privaten/Inkognito-Fenster** (für die Kundensicht)
- Eine optionale Titelseite (Gruppe, Namen, Case) wirkt professionell, ist aber nicht verlangt.
- Die Demo **mindestens einmal komplett durchspielen und stoppen**. Live-Demos dauern immer länger als gedacht.
- Macht vorher Screenshots der wichtigsten Ansichten als **Backup**, falls das WLAN oder Odoo ausfällt.

---

## 2. Die BPMN-Modelle und wie ihr sie erklärt

### BPMN 1 – „Einrichtung Online-Shop“ (der Case selbst)

![BPMN 1](bpmn/01_ScaleUp_SellOnline_Einrichtung.png)

- **Ein Pool** „MyOffice Inc.“ mit **zwei Lanes**: *Sales Manager (Sophia)* stellt die Anforderungen und testet, *Website-Verantwortliche/r* (im Case „You“) setzt in Odoo um.
- Innerhalb eines Pools verbinden **Sequenzflüsse** die Lanes (keine Nachrichtenflüsse, die gibt es nur zwischen Pools).
- Die Nummern **(1)–(7)** entsprechen den 7 Schritten im Scale-Up-PDF.
- **XOR-Gateway „Testkauf erfolgreich?“**: Bei „nein“ werden Fehler behoben und der Testkauf wird wiederholt (Schleife). Vor dem Testkauf steht deshalb ein **zusammenführendes XOR-Gateway**. Das entspricht der Regel aus der Vorlesung: *„Ein Pfeil rein und mehrere raus oder umgekehrt – nicht mischen!“*
- Aufgaben sind nach der Regel **[Objekt] + [Verb in Grundform]** beschriftet (z. B. „Homepage gestalten“).

### BPMN 2 – „Online-Bestellung“ (der Prozess, den der Shop danach unterstützt)

![BPMN 2](bpmn/02_ScaleUp_SellOnline_Bestellprozess.png)

- **Zwei Pools**: *Kunde* und *MyOffice Inc.* Über die Poolgrenze laufen **Nachrichtenflüsse** (gestrichelt), nie Sequenzflüsse (Vorlesung SW02: „Nachrichten als Lösung zu Poolgrenzenüberschreitung“).
- MyOffice startet mit einem **Nachrichten-Startereignis** „Online-Bestellung eingegangen“. Der Kunde wartet mit **empfangenden Nachrichten-Zwischenereignissen** auf Bestätigung und Lieferung (jeweils ein Pfeil rein, ein Pfeil raus).
