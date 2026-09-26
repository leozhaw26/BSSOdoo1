# Drehbuch: Scale-Up-Vorstellung „Sell Online“

**Gruppe:** Albin Ahmetaj · Cem Durdu · Leorat Krasniqi
**Dauer:** 15 Minuten Vortrag + 5 Minuten Fragen
**Instanz:** `https://edu-zhaw-3bss-2026-krasnleo.odoo.com`

**So ist das Drehbuch aufgebaut**

- Die Texte in den grauen Kästen (`>`) sind der **Sprechtext**. Ihr müsst ihn nicht auswendig lernen. Lest ihn ein paarmal durch und sagt es dann **in euren eigenen Worten** (frei sprechen zählt in der Bewertung).
- Die **📋 Regie**-Notizen sagen, was die Person gerade **klickt** und was auf dem Bildschirm **zu sehen** ist.
- ⏱ gibt an, wo ihr zeitlich stehen solltet.

---

## Vorbereitung (vor dem Start, ca. 2 Minuten)

📋 **Regie**

- **Ein Laptop am Beamer.** Wer spricht, steht am Laptop und klickt selbst. Die anderen stehen daneben.
- Folgende **Tabs sind offen**, in dieser Reihenfolge:

| Tab | Inhalt | Braucht |
|---|---|---|
| 1 | BPMN 1 „Einrichtung“ (PNG oder demo.bpmn.io) | Albin |
| 2 | BPMN 2 „Bestellprozess“ | Albin |
| 3 | Odoo-Backend, eingeloggt als Admin, App *Website* | Cem, Leorat |
| 4 | **Inkognito-Fenster** mit der Homepage (Kundensicht, nicht eingeloggt) | Cem, Leorat |

- Browser-Zoom auf 110–125 %, damit man hinten im Raum etwas sieht.
- Benachrichtigungen (WhatsApp, Teams usw.) ausschalten.
- Warenkorb im Inkognito-Fenster ist **leer**.
- Handy mit Backup-Screenshots liegt bereit.

---

## Teil 1 – Albin: Einstieg und BPMN (0:00–4:00)

### 1.1 Begrüssung (0:00–1:00)

📋 **Regie:** Tab 1 (BPMN 1) ist offen, aber noch nicht wichtig. Albin steht vorne und schaut ins Publikum, nicht auf den Bildschirm.

> Guten Tag zusammen. Wir sind Albin, Cem und Leorat, und wir stellen euch heute die Scale-Up-Fallstudie **„Sell Online“** vor.
>
> Kurz zur Ausgangslage: Die Firma **MyOffice Inc.** verkauft Büromöbel. Lokal ist sie für Qualität und Service bekannt, aber sie hat noch keinen Online-Auftritt. Das Ziel des Cases ist, mit Odoo einen **Online-Shop** aufzubauen, damit Kunden den Katalog anschauen, Produkte konfigurieren, online kaufen und ihre Bestellung verfolgen können.
>
> Im Case gibt es zwei Rollen: **Sophia**, die Sales Managerin, stellt die Anforderungen. Die **Website-Verantwortlichen**, also wir, setzen sie in Odoo um. Das passiert in **sieben Schritten**: Homepage gestalten, Produktseite erstellen, SEO verbessern, Produktvarianten hinzufügen, den Shop testen, Cross-Selling mit einer Garantie und zum Schluss einen Blogbeitrag schreiben.
>
> Unser Ablauf: Ich zeige euch zuerst den Prozess als **BPMN**. Danach zeigt Cem die Website live in Odoo, und Leorat zeigt den Verkauf mit einem Testkauf. Zum Schluss erzählen wir unsere **Learnings**.

### 1.2 BPMN 1 – Einrichtung des Online-Shops (1:00–2:30)

📋 **Regie:** Auf **Tab 1** (BPMN 1) klicken. Beim Erklären mit der Maus den jeweiligen Teil im Diagramm **zeigen**: zuerst die beiden Lanes, dann von links nach rechts dem Ablauf folgen, beim Gateway kurz stoppen.

> Das erste Modell zeigt den **Case selbst**, also wie der Shop eingerichtet wird.
>
> Wir haben **einen Pool**, MyOffice Inc., mit **zwei Lanes**: oben Sophia als Sales Managerin, unten die Website-Verantwortlichen. Weil beide in derselben Firma arbeiten, verbinden wir die Lanes mit normalen **Sequenzflüssen**.
>
> Der Prozess startet, wenn die Online-Präsenz beschlossen ist. Sophia legt die Anforderungen fest, dann installieren wir die eCommerce-App. Danach folgen die Schritte **eins bis vier** aus dem Case: Homepage, Produktseite, SEO und Varianten. Die Nummern im Diagramm entsprechen den Schritten im Scale-Up-PDF.
>
> Spannend ist der **Testkauf**, also Schritt fünf. Sophia testet den Shop, und danach kommt ein **exklusives Gateway**: „Testkauf erfolgreich?“ Wenn nein, beheben wir die Fehler und testen noch einmal. Das ist eine **Schleife**. Deshalb steht vor dem Testkauf ein **zusammenführendes** XOR-Gateway, wie in der Vorlesung: ein Pfeil rein und mehrere raus, oder umgekehrt, aber nie gemischt.
>
> Wenn der Test erfolgreich ist, legen wir die Garantie als optionales Produkt an und veröffentlichen den Blogbeitrag. Dann ist der Online-Shop live.

### 1.3 BPMN 2 – Der Bestellprozess (2:30–4:00)

📋 **Regie:** Auf **Tab 2** (BPMN 2) wechseln. Zuerst auf den oberen Pool (Kunde) zeigen, dann auf den unteren (MyOffice) und dabei die gestrichelten Nachrichtenflüsse von oben nach unten nachfahren.

> Die Einrichtung macht man **einmal**, das ist eigentlich eher ein **Projekt**. Der eigentliche **Geschäftsprozess**, der sich jeden Tag wiederholt, ist die **Online-Bestellung**. Den zeigt unser zweites Modell.
>
> Hier haben wir **zwei Pools**: oben den **Kunden**, unten **MyOffice**. Zwischen den Pools gibt es nur **Nachrichtenflüsse**, die gestrichelten Linien, denn Sequenzflüsse dürfen die Poolgrenze nicht überschreiten.
>
> Der Kunde besucht den Shop, wählt Farbe und Material und legt den Stuhl in den Warenkorb. Dann kommt ein **XOR-Gateway**: Will der Kunde die Garantie oder nicht? Das ist unser Cross-Selling aus Schritt sechs. Danach bestellt und bezahlt der Kunde.
>
> Bei MyOffice startet der Prozess mit einem **Nachrichten-Startereignis**: Die Bestellung ist eingegangen. Zahlung prüfen und Auftrag bestätigen sind **Service-Tasks**, man sieht das am Zahnrad. Die macht Odoo **automatisch**, ohne dass ein Mensch etwas tun muss. Dann bekommt der Kunde die Bestätigung per E-Mail.
>
> Danach teilt sich der Prozess mit einem **parallelen Gateway**: Das **Lager** versendet die Lieferung, und gleichzeitig erstellt die **Buchhaltung** die Rechnung. Erst wenn beides erledigt ist, ist die Bestellung abgewickelt.
>
> Wichtig: Webshop, Lager und Buchhaltung arbeiten alle **im gleichen System**, in Odoo. Die Bestellung muss niemand noch einmal abtippen. Das ist genau die **Integration**, die ein ERP-System ausmacht.

⏱ **Stand: ca. 4:00**

### Übergabe an Cem

> So sieht der Prozess auf dem Papier aus. **Cem** zeigt euch jetzt, wie wir die Website in Odoo aufgebaut haben.

📋 **Regie:** Albin tritt zur Seite, Cem übernimmt den Laptop.

---

## Teil 2 – Cem: Live-Demo Website & Content (4:00–8:30)

### 2.1 Homepage – Schritt 1 (4:00–5:15)

📋 **Regie:** Auf **Tab 4 (Inkognito)** wechseln, die Homepage ist zu sehen. Langsam nach unten scrollen: Cover-Bild → Kennzahlen-Block mit Verlauf → drei Spalten. Danach auf **Tab 3 (Admin)** wechseln, **Bearbeiten** klicken und zeigen, dass links die Blöcke erscheinen. **Nichts** verändern, danach **Verwerfen** klicken.

> Das ist unsere Homepage, so wie ein Kunde sie sieht. Ich bin hier bewusst **nicht eingeloggt**.
>
> Sophia wollte oben ein **Cover** mit einem Bürobild. Darunter kommt ein Block mit **Kennzahlen**: über 700 zufriedene Kunden, über 120 designte Produkte und Lieferungen in 15 Länder, mit einem **Farbverlauf** im Hintergrund. Und dann die drei Spalten: **You Customize, We Design, We Manufacture**.
>
> Wie haben wir das gemacht? Im Admin-Bereich klicke ich auf **Bearbeiten**. Links sehe ich jetzt alle Bausteine, die sogenannten Blöcke. Die zieht man einfach per **Drag & Drop** auf die Seite. Bilder, Farben und Verläufe stellt man rechts im Stil-Menü ein. Programmieren muss man dafür **nichts**.

### 2.2 Produktseite – Schritt 2 (5:15–6:15)

📋 **Regie:** Im Admin-Tab oben auf **+ Neu** klicken und zeigen, dass es „Produkt“ gibt. **Nicht** anlegen, das Fenster wieder schliessen. Dann im **Inkognito-Tab** auf **Shop** → **Office Chair** klicken. Auf Beschreibung, Preis und Bild zeigen.

> Im zweiten Schritt wollte Sophia den neuen **Office Chair** online verkaufen. Ein Produkt legt man direkt auf der Website an, über **Neu → Produkt**: Name, Preis und Steuer, fertig.
>
> Hier seht ihr die Produktseite im Shop. Der Preis ist **CHF 120**. Der Case rechnet in Dollar mit 15 % Steuer, unsere Schweizer Instanz aber in Franken mit **8.1 % MwSt**. Das haben wir so angepasst.
>
> Für die Beschreibung haben wir, wie im Case verlangt, die **KI-Funktion** im Texteditor verwendet. Man markiert den Text, klickt auf „KI“, und Odoo schlägt einen Text vor.

### 2.3 SEO – Schritt 3 (6:15–7:30)

📋 **Regie:** Im **Admin-Tab** zur **Homepage** gehen → oben im Menü **Site → SEO optimieren**. Der Dialog öffnet sich. Nacheinander zeigen: Titel, Beschreibung, **Google-Vorschau** rechts, Keyword **„office furniture“** mit den Häkchen und die **vorgeschlagenen Begriffe**. Danach **Verwerfen/Schliessen**.

> Im dritten Schritt hat Sophia gemerkt: Wenn man bei Google „office furniture“ sucht, findet man uns nicht. Deshalb haben wir die **Suchmaschinenoptimierung** verbessert.
>
> Das geht direkt auf der Seite mit **SEO optimieren**. Hier legen wir den **Titel** und die **Beschreibung** fest, die bei Google erscheinen. Rechts sieht man eine **Vorschau**, wie das Suchergebnis aussehen wird.
>
> Unten haben wir das Keyword **„office furniture“** hinzugefügt. Odoo zeigt mit Häkchen, ob das Keyword im Titel, in der Beschreibung und in den Überschriften vorkommt. Daneben schlägt Odoo **verwandte Suchbegriffe** vor, zum Beispiel „store“ oder „center“. Einige davon haben wir in die Überschrift der Homepage übernommen.

### 2.4 Blogbeitrag – Schritt 7 (7:30–8:30)

📋 **Regie:** Im **Inkognito-Tab** im Menü auf **Neuigkeiten** klicken → Beitrag **„Entdecken Sie unsere 3-Jahres-Garantie“** öffnen. Auf das Coverbild und den Text zeigen.

> Den Blog zeige ich schon jetzt, obwohl er im Case Schritt sieben ist, weil er zum Thema Website passt. Unter **Neuigkeiten** haben wir einen Beitrag über unsere **3-Jahres-Garantie** veröffentlicht, mit einem Coverbild und einem Link zum Bürostuhl.
>
> Kleiner Tipp aus unserer Erfahrung: Neue Beiträge sind in Odoo zuerst **nicht veröffentlicht**. Als Admin sieht man sie trotzdem, deshalb sollte man immer in einem **Inkognito-Fenster** prüfen, was ein Besucher wirklich sieht. Dazu erzählen wir am Schluss noch mehr.

⏱ **Stand: ca. 8:30**

### Übergabe an Leorat

> Jetzt haben wir eine Website mit Produkt und Blog, und diese Garantie kann man jetzt auch direkt beim Stuhl dazukaufen. **Leorat** zeigt euch, wie aus der Website ein Verkauf wird und was im Hintergrund passiert.

📋 **Regie:** Cem tritt zur Seite, Leorat übernimmt den Laptop.

---

## Teil 3 – Leorat: Live-Demo Verkauf & Integration (8:30–13:30)

### 3.1 Produktvarianten – Schritt 4 (8:30–9:45)

📋 **Regie:** Im **Admin-Tab**: **Website → eCommerce → Produkte → Office Chair** öffnen → Tab **Attribute & Varianten**. Auf die zwei Zeilen *Material* und *Farbe* zeigen. Dann das Attribut **Farbe** öffnen und **Anzeigetyp: Farbe** mit den Farbwerten zeigen. Zurück zum Produkt, auf den Smart-Button **6 Varianten** zeigen.

> Die Stühle haben sich gut verkauft, aber die Kunden wollten **verschiedene Farben und Materialien**. Deshalb haben wir im vierten Schritt **Produktvarianten** eingerichtet.
>
> Hier im Produkt haben wir zwei **Attribute**: das Material, also Stoff oder Leder, und die Farbe, also Grau, Weiss oder Violett. Bei der Farbe haben wir den **Anzeigetyp „Farbe“** gewählt und die genauen **RGB-Werte aus dem Case** als Farbcode eingegeben. So erscheinen im Shop kleine Farbkreise statt nur Text.
>
> Zwei Materialien mal drei Farben ergibt **sechs Varianten**. Für Odoo ist jede Variante ein eigenes Produkt, aber alle hängen an einer gemeinsamen Vorlage.

### 3.2 Garantie als optionales Produkt – Schritt 6 (9:45–10:30)

📋 **Regie:** Im Office Chair auf den Tab **Verkauf** wechseln → Feld **Optionale Produkte** mit „Garantie: 3 Jahre“ zeigen. Kurz auf die Garantie klicken und **Produkttyp: Dienstleistung** und Preis **50** zeigen.

> Im sechsten Schritt wollte Sophia **Cross-Selling**, also zusätzliche Produkte vorschlagen. Wir haben dafür ein neues Produkt **„Garantie: 3 Jahre“** für 50 Franken erstellt.
>
> Wichtig ist der **Produkttyp**: Die Garantie ist eine **Dienstleistung**, kein physisches Produkt. Warum das wichtig ist, seht ihr gleich beim Testkauf.
>
> Beim Bürostuhl haben wir die Garantie als **optionales Produkt** hinterlegt.

### 3.3 Testkauf – Schritt 5 (10:30–12:00)

📋 **Regie:** Zum **Inkognito-Tab** wechseln → **Shop → Office Chair** → Farbe **Violett**, Material **Stoff** → **In den Warenkorb**. Das **Pop-up mit der Garantie** erscheint → Garantie hinzufügen → **Zur Kasse** → Adresse eingeben (vorher bereitgelegte Testdaten) → mit **Demo**-Zahlung bezahlen → Bestätigungsseite zeigen.
Tipp: Die Adresse vorher einmal eintippen und nicht live suchen. Das spart 30 Sekunden.

> Jetzt der Test, so wie im fünften Schritt: Wir kaufen den **violetten Stuhl**, als ganz normaler Kunde im Inkognito-Fenster.
>
> Ich wähle Violett und Stoff und lege den Stuhl in den Warenkorb. Und hier seht ihr das Cross-Selling: Odoo bietet mir **automatisch die Garantie** an. Die nehme ich dazu.
>
> Im Warenkorb sieht man jetzt Stuhl plus Garantie, inklusive **MwSt**. Ich gehe zur Kasse, gebe die Adresse ein und bezahle. Weil das ein Test ist, haben wir den Zahlungsanbieter **„Demo“ im Testmodus** aktiviert. Es fliesst also kein echtes Geld. Im echten Betrieb würde man zum Beispiel Stripe oder PayPal verwenden.
>
> Die Bestellung ist durch, und der Kunde bekommt eine **Bestätigung**. Das ist genau das Nachrichten-Zwischenereignis „Bestellbestätigung erhalten“ aus unserem BPMN.

### 3.4 Integration im Backend (12:00–13:30)

📋 **Regie:** Zum **Admin-Tab** wechseln → **Website → eCommerce → Aufträge** (oder **Verkauf → Aufträge**) → die gerade erstellte Bestellung ganz oben öffnen. Zeigen: Status **Verkaufsauftrag** (bestätigt) → Smart-Button **Lieferung** öffnen, **nur der Stuhl** steht drin → zurück → Smart-Button **Rechnung** öffnen.
Falls BPMN 2 griffbereit ist, am Ende kurz auf Tab 2 wechseln und auf die Lanes Lager und Buchhaltung zeigen.

> Und jetzt kommt das Spannendste: Was passiert im Hintergrund?
>
> Hier im Backend ist die Bestellung schon da, und zwar **automatisch bestätigt** als Verkaufsauftrag. Niemand musste sie abtippen.
>
> Hier ist die **Lieferung** für das Lager. Achtung: Drin ist **nur der Stuhl**, nicht die Garantie, denn die Garantie ist eine Dienstleistung und muss nicht verschickt werden. Deshalb war der Produkttyp so wichtig.
>
> Und hier ist die **Rechnung** für die Buchhaltung.
>
> Das ist genau unser **BPMN 2, live**: Webshop, Lager und Buchhaltung arbeiten mit **denselben Daten in einem System**. Das ist der grosse Vorteil eines ERP-Systems gegenüber einzelnen Insellösungen.

⏱ **Stand: ca. 13:30**

### Übergabe an die Learnings

> Das war unser Prozess live in Odoo. Zum Schluss erzählt jede und jeder von uns, was wir **gelernt** haben und wo es **Herausforderungen** gab.

📋 **Regie:** Alle drei stehen jetzt nebeneinander vorne. Der Bildschirm kann auf BPMN 2 bleiben.

---

## Teil 4 – Learnings & Herausforderungen (13:30–15:00, je ca. 30 Sekunden)

### Albin – Prozess vs. Projekt

> Mein Learning: Uns ist aufgefallen, dass es beim Case eigentlich um **zwei verschiedene Dinge** geht. Die Einrichtung des Shops macht man einmal, das ist eher ein **Projekt**. Die Online-Bestellung wiederholt sich jeden Tag, das ist ein echter **Geschäftsprozess**. Deshalb haben wir **zwei BPMN-Modelle** gemacht. Beim Modellieren haben uns die Regeln aus der Vorlesung geholfen, zum Beispiel, dass zwischen Pools nur Nachrichtenflüsse erlaubt sind.

### Cem – Zwei Websites in einer Instanz

> Meine Herausforderung: Wir haben den Blogbeitrag veröffentlicht, aber im Inkognito-Fenster kam eine **404-Seite**. Die Ursache: In unserer Odoo-Instanz gab es **zwei Websites**, „My Website“ und „Website“. Wir haben alles auf der einen gebaut, die Besucher sind aber auf der anderen gelandet. Gemerkt haben wir es am anderen Menü und an der anderen Fusszeile. Die Lösung war, in den Einstellungen die **Domain** der richtigen Website zuzuordnen. **Unser Tipp an euch:** Prüft alles immer auch im Inkognito-Fenster.

### Leorat – Integration und Produkttyp

> Mein Learning ist die **Integration**: Eine einzige Online-Bestellung erzeugt automatisch einen Auftrag, eine Lieferung und eine Rechnung, ohne dass man etwas zweimal eingeben muss. Und: Der **Produkttyp** steuert den Prozess. Weil die Garantie eine Dienstleistung ist, entsteht dafür keine Lieferung. Noch ein Tipp: Damit die Garantie im Shop erscheint, muss sie **selbst auch auf der Website veröffentlicht** sein.

### Abschluss (Albin)

> Das war unsere Vorstellung von „Sell Online“. Vielen Dank fürs Zuhören. Jetzt beantworten wir gerne eure **Fragen**.

⏱ **Stand: ca. 15:00**

---

## Fragerunde (15:00–20:00) – wer antwortet worauf?

📋 **Regie:** Wer den Teil gezeigt hat, antwortet. Weiss jemand nicht weiter, darf eine andere Person ergänzen. Das wirkt als gute Zusammenarbeit. Wenn nötig, schnell den passenden Tab zeigen.

| Thema der Frage | Antwortet | Kurze Antwort |
|---|---|---|
| Warum zwei BPMN-Modelle? | Albin | Einrichtung = einmaliges Projekt, Bestellung = wiederkehrender Prozess mit Integration über Abteilungen |
| Warum gestrichelte Linien zwischen den Pools? | Albin | Sequenzflüsse dürfen die Poolgrenze nicht überschreiten, zwischen Organisationen gibt es nur Nachrichten |
| Warum UND- statt XOR-Gateway bei Lieferung/Rechnung? | Albin | Beides muss passieren und läuft parallel. Beim XOR würde nur ein Pfad ausgeführt |
| Was passiert, wenn die Zahlung fehlschlägt? | Albin / Leorat | Der Auftrag wird nicht bestätigt, es gibt keine Lieferung. Im BPMN könnte man ein XOR „Zahlung erfolgreich?“ ergänzen |
| Wie wird man bei Google gefunden? | Cem | SEO pro Seite: Titel, Beschreibung, Keywords. Odoo erstellt zusätzlich automatisch eine Sitemap |
| Musste man etwas programmieren? | Cem | Nein, alles per Konfiguration: Blöcke per Drag & Drop, Einstellungen, Formulare |
| Darf man ein anderes Design als im PDF nehmen? | Cem | Ja, das PDF sagt selbst „choose your favorite“. Umgesetzt werden müssen die Anforderungen von Sophia |
| Unterschied optionale Produkte / Zubehör / Alternativen? | Leorat | Optional = Pop-up beim Hinzufügen (Cross-Sell), Zubehör = Vorschlag im Warenkorb, Alternative = anderes, oft teureres Produkt (Upsell) |
| Kann eine Variante mehr kosten (z. B. Leder)? | Leorat | Ja, über einen Preisaufschlag pro Attributwert, z. B. Leder +30 |
| Warum kostet es nicht 138 $ wie im PDF? | Leorat | Schweizer Instanz: CHF und 8.1 % MwSt statt $ und 15 % |
| Was würdet ihr als Nächstes machen? | alle | Automatische Rechnung nach Zahlung, E-Mail-Vorlagen, Nachbestellregel für Stühle im Einkauf |

Weitere Fragen mit Antworten stehen im Leitfaden (`README.md`, Kap. 6).

---

## Notfallplan

| Problem | Was tun |
|---|---|
| WLAN oder Odoo fällt aus | Die Backup-Screenshots zeigen und genau gleich weitererzählen. Nicht entschuldigen, einfach weitermachen |
| Das Garantie-Pop-up erscheint nicht | Garantie manuell über den Shop in den Warenkorb legen und erwähnen: „Normalerweise erscheint hier das Pop-up.“ Danach prüfen: Ist die Garantie veröffentlicht und beim Stuhl als optionales Produkt hinterlegt? |
| Die Zahlung geht nicht durch | Einen vorbereiteten Testauftrag von vorher im Backend zeigen, deshalb **vorher einen Testkauf machen und nicht löschen** |
| Die Zeit wird knapp (Stand über 10:00 bei Leorat) | Varianten (3.1) nur kurz im Shop zeigen statt im Backend, direkt zum Testkauf |
| Eine Frage, die niemand beantworten kann | „Gute Frage, das haben wir nicht getestet. Wir vermuten …, schauen es aber gerne nach.“ Ehrlich sein ist besser als raten |

---

## Letzte Probe – Checkliste

- [ ] Einmal komplett zu dritt mit Stoppuhr durchgespielt: ≤ 15 Minuten
- [ ] Jede Person kennt ihre Übergabe-Sätze
- [ ] Testkauf vorher einmal gemacht (dient als Backup), Warenkorb im Inkognito-Fenster danach leer
- [ ] Testadresse für den Checkout bereit
- [ ] Tabs 1–4 offen, Zoom eingestellt, Benachrichtigungen aus
- [ ] Backup-Screenshots auf dem Handy
