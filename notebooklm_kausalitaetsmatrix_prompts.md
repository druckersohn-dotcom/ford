# Kausalitätsmatrix § 612a BGB: Prompt-Kette für NotebookLM

Verfahren Matt ./. octeo MULTISERVICES GmbH, ArbG Duisburg, 4 Ca 1222/26.

## Anleitung

Voraussetzungen vor Prompt 1:
- Chat-Konfiguration v3 ist aktiv.
- Alle Quellen im Notebook sind angehakt. Prüfe das vor jedem Prompt, NotebookLM merkt sich Abwahlen.
- Quellen, die nur als Bild oder Scan ohne Textebene vorliegen, vorher durch eine Textfassung ersetzen oder ergänzen. Sonst sieht NotebookLM sie nicht.

Reihenfolge:
1. Prompt 1 im Chat. Antwort als Notiz speichern, Titel: "INVENTAR".
2. Prompt 2 im Chat. Antwort als Notiz speichern, Titel: "EREIGNISSE". Bricht die Antwort ab: "Setze bei Tabelle [Buchstabe] Zeile [Nr] fort, keine Wiederholung." senden.
3. Notizen INVENTAR und EREIGNISSE über "In Quelle umwandeln" zu Quellen machen.
4. Prompt 3 als eigener Bericht im Studio (Variante 3a). Fehlen im Bericht Fundstellen oder Quellenzitate, stattdessen Variante 3b im Chat. Ergebnis als Notiz "MATRIX" speichern und ebenfalls in eine Quelle umwandeln.
5. Prompt 4 im Chat.
6. Nach jeder Lückenschließung (neue Anlage im Notebook) nur Prompt 4 erneut senden.

Jeder Prompt liegt unter 10.000 Zeichen.

---

## PROMPT 1: INVENTAR

Aufgabe: Inventar aller Quellen dieses Notebooks. Noch keine Bewertung, keine Zusammenfassung, keine Auslassung.

Gehe jede Quelle einzeln durch, in der Reihenfolge der Quellenliste. Enthält eine Quelle mehrere Dokumente (Anlagenkonvolut, E-Mail-Verlauf, mehrere Abrechnungen in einer Datei), bekommt jedes enthaltene Dokument eine eigene Zeile mit Unternummer (3.1, 3.2).

Tabelle, eine Zeile je Dokument:
Nr | Quellenname exakt wie im Notebook | Dokumentart (E-Mail, Brief, Fax, Protokoll, Gedächtnisprotokoll, Abrechnung, Stundenaufzeichnung, Systemprotokoll, Dienstplan, Vertrag, Tarifvertrag, Schriftsatz, Foto, sonstiges) | Aussteller/Absender | Empfänger | Datum des Dokuments | Zeitraum, den es betrifft | Vorgänge, die es belegt (Stichwort mit Datum, Fundstelle Seite) | Relevanz | Umfang (Seiten)

Spalte Relevanz, Mehrfachnennung möglich:
R = Rechtsausübung des Klägers (Lohn- oder Tarifforderung, Widerspruch, Gewerkschaftsbeitritt, Beschwerde nach §§ 84, 85 BetrVG, Anwaltsschreiben, Klage, Verweigerung einer Weisung, Auskunftsverlangen)
M = Maßnahme von octeo gegen den Kläger (Entzug von Objekt, Stunden, Diensten, Schicht; Versetzung; Abmahnung; Kontrolle; Kündigung; Nichtzahlung)
K = Kenntnis oder Entscheidung: belegt, wer bei octeo wann von einer Rechtsausübung wusste oder wer eine Maßnahme angeordnet hat
G = Grund oder Entlastung: Stelle, die octeo als sachlichen Grund, Pflichtverstoß des Klägers oder vorbestehende Planung zitieren könnte
V = Vergleichspersonen: Kollegen, deren Behandlung sich vergleichen lässt
E = Entgelt: Stundensatz, Stunden, Zulagen, Zuschläge, Abrechnung
B = Betriebsrat: Beteiligung, Anhörung, Beschwerde
0 = keine Relevanz für Kausalität

Nach der Tabelle:
1. Gesamtzahl der Quellen im Notebook und Gesamtzahl der Zeilen. Weichen sie ab: Grund je Fall.
2. Liste der Quellen, deren Inhalt nicht oder nur teilweise lesbar war (Scan ohne Text, Bild, abgeschnitten), mit Angabe, was fehlt.
3. Liste der Dokumente ohne erkennbares Datum.
4. Liste der Dokumente, in denen Namen von octeo-Mitarbeitern mit Funktion vorkommen: Name | Funktion | Quelle.

Regeln:
- Jede Zeile nur aus der Quelle selbst, nichts aus dem Chatverlauf oder aus Rechtswissen ergänzen.
- Keine Quelle als "ähnlich wie oben" zusammenfassen.
- Unsichere Zuordnung mit [PRÜFEN] markieren statt zu raten.
- Reicht die Antwortlänge nicht, Tabelle vollständig liefern und erst danach die Listen 1 bis 4; notfalls "FORTSETZUNG FOLGT" schreiben und auf Aufforderung fortsetzen.

Selbsttest vor der Ausgabe: Steht jede Quelle des Notebooks in der Tabelle? Hat jede Zeile eine Fundstelle in der Spalte Vorgänge?

---

## PROMPT 2: EREIGNISEXTRAKTION

Grundlage: Quelle INVENTAR sowie alle Originalquellen. Aufgabe: alle Ereignisse mit Bezug zu § 612a BGB in fünf Tabellen erfassen. Noch keine Kausalitätswertung; die kommt in einem späteren Schritt.

Vorgehen: Gehe das Inventar Zeile für Zeile durch. Jede Zeile mit Relevanz R, M, K, G, V oder B muss in mindestens einer der Tabellen A bis E mit Fundstelle auftauchen. Ein Vorgang, der in mehreren Quellen belegt ist, bekommt eine Zeile mit allen Fundstellen.

TABELLE A: Rechtsausübungen des Klägers
Nr | Datum | Handlung (wörtlich oder sinngemäß, kurz) | Form (mündlich, Brief, E-Mail, Fax, über Anwalt, Klage) | Adressat bei octeo (Name, Funktion) | Zugang oder Kenntnisnahme belegt durch (Quelle, Seite) | Weitere Personen bei octeo, die davon erfuhren (Name, Datum, Beleg) | Reaktion von octeo mit Datum und Beleg | Lücke

Erfasse mindestens: Tarifforderung 07.11.2025, Gewerkschaftsbeitritt (und ob octeo davon wusste), Lohnwiderspruch 31.01.2026, Zahlungsaufforderung 23.02.2026, Fax 12.03.2026, Beschwerden nach §§ 84, 85 BetrVG, Klageerhebung, jede weitere in den Quellen belegte Geltendmachung, Verweigerung oder Beanstandung einer Weisung, Auskunftsverlangen.

TABELLE B: Maßnahmen von octeo gegen den Kläger
Nr | Datum der Anordnung | Datum des Zugangs beim Kläger | Datum des Wirksamwerdens | Maßnahme | Angeordnet durch (Name, Funktion) | Umgesetzt durch | Form (mündlich, E-Mail, Dienstplan, Brief) | Begründung von octeo, wörtlich aus der Quelle, oder "keine Begründung in den Quellen" | Erstmals dokumentiert am (Datum der frühesten Quelle, die die Maßnahme oder ihre Planung erwähnt) | Wirkung auf den Kläger (Stunden pro Monat, Zuschläge, Arbeitsort, Arbeitszeit, Entgelt in EUR, soweit in den Quellen) | Betriebsrat beteiligt (ja, nein, unbekannt; Beleg) | Quellen | Lücke

Erfasse mindestens: Drohung vom 07.11.2025, Entzug Sporthalle Hitzestraße 06.02.2026, Versetzung des Arbeitsorts, Wechsel in die Spätschicht, Entzug der Wochenenddienste, Kürzung oder Verschiebung von Stunden, Nichtzahlung oder Kürzung von Entgelt, Abmahnungen, Arbeitsplatzinspektion 16./17.06.2026, Fotoaufnahmen, Beschattung oder GPS-Ortung, Vernichtung der Original-Stundenzettel, fristlose Kündigung 19.06.2026, Vorgänge nach der Kündigung (Zeugnis, Abrechnung, Herausgabe), jede weitere in den Quellen belegte Schlechterstellung.

TABELLE C: Kenntnis- und Entscheiderkette
Person bei octeo | Funktion | Wusste von welcher Rechtsausübung (Nr aus A) seit wann (Beleg) | Hat welche Maßnahme (Nr aus B) angeordnet oder umgesetzt (Beleg) | Äußerungen zum Motiv, wörtlich mit Quelle

TABELLE D: Entlastungsstellen
Jede Stelle in den Quellen, die octeo zu seinen Gunsten zitieren kann: Nr | Quelle, Seite | Inhalt wörtlich | Betrifft Maßnahme (Nr aus B) | Datum der Entstehung des Dokuments | Entstanden vor oder nach dem 31.01.2026 | Vor oder nach dem 07.11.2025 | Was octeo daraus machen wird (ein Satz)
Hierzu zählen: Hinweise auf Auslastung, Belegungspläne, Umstrukturierung, Kundenwünsche, Pflichtverstöße oder Beanstandungen gegen den Kläger, Krankheitszeiten, frühere Versetzungen vor dem 07.11.2025, Vergleichsangebote, Äußerungen des Klägers, die gegen ihn verwendet werden können.

TABELLE E: Vergleichspersonen und bisherige Praxis
Person oder Gruppe | Tätigkeit und Objekt | Was ihr zugewiesen, belassen oder entzogen wurde, mit Datum | Hat sie Ansprüche geltend gemacht (ja, nein, unbekannt) | Quelle | Bedeutung für den Vergleich (ein Satz)
Zusätzlich: bisherige Praxis gegenüber dem Kläger vor dem 07.11.2025 (Objekte, Schichten, Wochenenddienste, Stunden pro Monat) mit Quelle.

Regeln:
- Nur Quelleninhalt. Was nicht in den Quellen steht: [BELEG FEHLT] in der Spalte Lücke, mit Angabe, welches Dokument den Beleg liefern würde (zum Beispiel "Dienstplan KW 06/2026", "E-Mail der Weisung vom 06.02.2026", "Anhörung Betriebsrat § 102 BetrVG").
- Daten immer als TT.MM.JJJJ. Unklares Datum: [DATUM] plus die Eingrenzung aus der Quelle.
- Wörtliche Zitate in Anführungszeichen mit Seite.
- Keine Zeile ohne Quelle.
- Widersprechen sich Quellen (zwei Daten, zwei Stundenzahlen): beide Angaben mit Quelle nennen, Zeile mit [WIDERSPRUCH] markieren.

Abschluss: Liste der Inventar-Zeilen mit Relevanz R, M, K, G, V oder B, die in keiner Tabelle vorkommen, mit Grund. Danach "FORTSETZUNG FOLGT", falls die Antwortlänge nicht gereicht hat.

---

## PROMPT 3a: KAUSALITÄTSMATRIX (Studio, eigener Bericht)

Rolle: Juristischer Zuarbeiter auf Klägerseite im Verfahren Matt ./. octeo MULTISERVICES GmbH (ArbG Duisburg, 4 Ca 1222/26). Adressat ist der Anwalt des Klägers; der Bericht muss ohne Umschreiben in einen Schriftsatz übernommen werden können. Dritte Person ("der Kläger", "die Beklagte"), keine Anrede, kein Vorspann, kein Hinweis auf KI oder fehlende Rechtsberatung. Parteiisch in der Wertung, präzise in der Subsumtion. Schwache Punkte einmal benennen und als [SCHWACH] markieren.

Quellenregeln: Jede Tatsache ausschließlich aus den Quellen, mit Fundstelle (Quellenname, Seite). Grundlage sind vorrangig die Quellen INVENTAR und EREIGNISSE, gegengeprüft an den Originalquellen. Fehlt ein Beleg: [BELEG FEHLT] mit Angabe des fehlenden Dokuments. Nichts ergänzen, nichts glätten. Normen mit Absatz; Aktenzeichen nur, wenn sicher, sonst "(Az. prüfen)".

Rechtlicher Rahmen: § 612a BGB. Tatbestand: (1) zulässige Rechtsausübung, (2) Benachteiligung, (3) Kausalität; die Rechtsausübung muss tragender Beweggrund sein, ein bloßer äußerer Anlass genügt nicht (BAG 23.04.2009 – 6 AZR 189/08, Az. prüfen). Beweislast für alle drei Merkmale beim Kläger; keine Beweislastumkehr. Der Beweis wird über Indizien in der Gesamtwürdigung nach § 286 Abs. 1 ZPO geführt. Die Beklagte trifft die sekundäre Darlegungslast für ihre Motive (§ 138 Abs. 2 ZPO); nicht substanziiert Bestrittenes gilt als zugestanden (§ 138 Abs. 3 ZPO). Nie schreiben, die Beklagte müsse die fehlende Kausalität beweisen.

Aufbau des Berichts:

1. ÜBERSICHTSMATRIX
Zeilen: alle Rechtsausübungen des Klägers (Tabelle A aus EREIGNISSE). Spalten: alle Maßnahmen der Beklagten (Tabelle B). Zelle: Abstand in Tagen von der Rechtsausübung bis zur Anordnung der Maßnahme, dahinter die Indizstärke: +++ stark, ++ mittel, + schwach, 0 kein Indiz, X zeitlich ausgeschlossen (Maßnahme liegt vor der Rechtsausübung oder vor der Kenntnis des Entscheiders). Jede Zelle ausfüllen, keine leer lassen.

2. ZELLBLÄTTER
Für jedes Paar mit Indizstärke + oder höher ein Block mit genau diesen Punkten:
a) Abstand in Tagen; Datum der Rechtsausübung, Datum der Kenntnis des Entscheiders, Datum der Anordnung, je mit Fundstelle.
b) Kenntnis: Kannte die anordnende Person die Rechtsausübung vor der Anordnung? Beleg oder [BELEG FEHLT].
c) Sachlicher Grund: Gibt es in den Quellen einen Grund, der vor der Rechtsausübung dokumentiert ist? Ja mit Fundstelle und Datum, oder nein. Begründung der Beklagten in der Quelle wörtlich, oder "keine Begründung dokumentiert".
d) Abweichung von der bisherigen Praxis und Vergleichspersonen (Tabelle E), mit Fundstelle.
e) Muster: weitere Maßnahmen innerhalb von 30 Tagen nach derselben Rechtsausübung, Nr aus Tabelle B.
f) Beteiligung des Betriebsrats: ja, nein, unbekannt; Beleg.
g) Motivbelege: wörtliche Äußerungen der Beklagten, die auf das Motiv schließen lassen (Tabelle C).
h) Entlastung: alles aus Tabelle D, das diese Zelle betrifft, mit Datum der Entstehung vor oder nach der Rechtsausübung, und Entgegnung in je einem Satz.
i) Indizstärke mit Begründung in zwei Sätzen.
j) Beweisantritte: Urkunde (Quellenname), Zeuge (Name, Funktion, Beweisthema), Parteivernehmung, Vorlageantrag nach § 142 ZPO (Dienstpläne, Belegungsplan, Systemprotokolle, Weisungs-E-Mail, Betriebsratsanhörung).
k) Lücken: [BELEG FEHLT] mit Dokument, das die Lücke schließen würde.

3. GESAMTWÜRDIGUNG
Die Indizienkette in der Reihenfolge ihrer Stärke, als zusammenhängender Vortrag für den Schriftsatz. Formel: "Die Indizien tragen den Vollbeweis, solange die Beklagte keinen dokumentierten, vor dem 31.01.2026 angelegten sachlichen Grund darlegt." Getrennt für den Entzug der Sporthalle, die Folgemaßnahmen und die Kündigung vom 19.06.2026.

4. DIE SCHWÄCHSTEN STELLEN
Die drei Zellen, bei denen die Beklagte am ehesten einen sachlichen Grund belegen kann, mit [SCHWACH] und dem Dokument, das die Lage drehen würde.

5. VORTRAG DER BEKLAGTEN AUS DENSELBEN QUELLEN
Was die Beklagte aus den Quellen gegen den Kläger zitieren wird, je mit Fundstelle und Entgegnung.

6. LÜCKENLISTE
Alle [BELEG FEHLT] aus den Zellblättern, sortiert nach Wirkung auf die Kausalität, mit dem jeweils fehlenden Dokument und dem Weg, es zu beschaffen (Vorlageantrag § 142 ZPO, Auskunft, Zeuge, eigener Bestand des Klägers).

Stil: Tabellen für Matrix und Lückenliste. Zahlen statt Adjektive. Keine Hedging-Ketten, keine Floskeln. Jede Behauptung mit Fundstelle oder Marker.

---

## PROMPT 3b: KAUSALITÄTSMATRIX (Chat, Fallback)

Grundlage: Quellen INVENTAR und EREIGNISSE, gegengeprüft an den Originalquellen. Beweislast für § 612a BGB liegt vollständig beim Kläger; Indizien in der Gesamtwürdigung nach § 286 Abs. 1 ZPO, sekundäre Darlegungslast der Beklagten nach § 138 Abs. 2 ZPO. Keine Beweislastumkehr behaupten.

Liefere in dieser Reihenfolge, jeweils mit Fundstellen:

1. ÜBERSICHTSMATRIX: Zeilen = Rechtsausübungen (Tabelle A), Spalten = Maßnahmen (Tabelle B). Zelle = Abstand in Tagen bis zur Anordnung plus Indizstärke (+++ stark, ++ mittel, + schwach, 0 keines, X zeitlich ausgeschlossen). Keine Zelle leer.

2. ZELLBLÄTTER für jedes Paar ab Stärke +, je mit: a) Abstand in Tagen und drei Daten (Rechtsausübung, Kenntnis des Entscheiders, Anordnung); b) Kenntnis des Entscheiders mit Beleg; c) sachlicher Grund vor der Rechtsausübung dokumentiert: ja mit Fundstelle und Datum, oder nein; Begründung der Beklagten wörtlich oder "keine Begründung dokumentiert"; d) Abweichung von bisheriger Praxis und Vergleichspersonen; e) weitere Maßnahmen binnen 30 Tagen; f) Betriebsrat beteiligt; g) Motivbelege wörtlich; h) Entlastungsstellen aus Tabelle D mit Entstehungsdatum und Entgegnung; i) Indizstärke mit zwei Sätzen Begründung; j) Beweisantritte: Urkunde, Zeuge mit Beweisthema, Parteivernehmung, Vorlageantrag § 142 ZPO; k) Lücken als [BELEG FEHLT] mit fehlendem Dokument.

3. GESAMTWÜRDIGUNG als Schriftsatzvortrag, getrennt für Sporthalle, Folgemaßnahmen, Kündigung. Formel: "Die Indizien tragen den Vollbeweis, solange die Beklagte keinen dokumentierten, vor dem 31.01.2026 angelegten sachlichen Grund darlegt."

4. DIE DREI SCHWÄCHSTEN ZELLEN mit [SCHWACH] und dem Dokument, das die Lage drehen würde.

5. VORTRAG DER BEKLAGTEN aus denselben Quellen, mit Fundstelle und Entgegnung.

6. LÜCKENLISTE, sortiert nach Wirkung auf die Kausalität, mit Beschaffungsweg.

Antwort zu lang: erst Matrix und Zellblätter vollständig, dann "FORTSETZUNG FOLGT"; die Abschnitte 3 bis 6 auf Aufforderung.

---

## PROMPT 4: VOLLSTÄNDIGKEITSKONTROLLE

Grundlage: Quellen INVENTAR, EREIGNISSE, MATRIX und alle Originalquellen. Aufgabe: prüfen, ob die Matrix wirklich alles aus dem Notebook verwertet, und was fehlt.

1. ABGLEICH QUELLE GEGEN MATRIX
Tabelle: Nr aus INVENTAR | Quellenname | Relevanz laut Inventar | Zitiert in Zelle(n) der Matrix (Zeile/Spalte) oder "nicht zitiert" | Falls nicht zitiert: Grund (irrelevant, übersehen, nur Entgelt) | Was die Quelle zur Kausalität beitragen würde (ein Satz mit Fundstelle)
Jede Quelle mit Relevanz R, M, K, G, V oder B, die "nicht zitiert" und nicht "irrelevant" ist, gilt als übersehen.

2. NACHTRAG
Für jede übersehene Quelle: Welche Zelle der Matrix ändert sich, in welche Richtung (stärker, schwächer), mit Fundstelle. Gegebenenfalls neue Zeile oder Spalte, falls die Quelle eine bisher nicht erfasste Rechtsausübung oder Maßnahme belegt.

3. WIDERSPRÜCHE
Alle Stellen, an denen Quellen einander widersprechen (Daten, Stunden, Beträge, Namen, Reihenfolge): Quelle 1 mit Angabe | Quelle 2 mit Angabe | Betroffene Zelle | Welche Version für den Kläger günstiger ist und wie der Widerspruch aufzulösen ist.

4. ERWARTBARE, ABER FEHLENDE DOKUMENTE
Dokumente, die nach dem Ablauf existieren müssen, aber in keiner Quelle vorliegen. Prüfe mindestens: Weisung zum Entzug der Sporthalle in Textform; Dienst- und Belegungspläne vor und nach dem 06.02.2026; Zugangsnachweise für 31.01., 23.02. und 12.03.2026; Anhörung des Betriebsrats nach § 102 Abs. 1 BetrVG zur Kündigung; Beteiligung nach § 99 Abs. 1 BetrVG zu Versetzung und Schichtwechsel; Arbeitsvertrag mit Ausschlussklausel; Mitgliedsbestätigung IG BAU; Protokoll oder Vermerk zur Inspektion 16./17.06.2026; Kündigungsschreiben mit Begründung; Antworten von octeo auf die Geltendmachungen; Zeiterfassung von octeo für 01/2023 bis 06/2026.
Tabelle: Dokument | Wer hat es (Kläger, Beklagte, Betriebsrat, Dritte) | Welche Zelle es betrifft | Beschaffungsweg (eigener Bestand, Vorlageantrag § 142 ZPO, Auskunft, Zeuge, Betriebsrat) | Priorität 1 bis 3 nach Wirkung auf die Kausalität

5. RÜCKFRAGEN AN DEN ANWALT
Nummerierte Liste. Nur Fragen, deren Antwort eine Zelle der Matrix verändert. Zu jeder Frage: betroffene Zelle und warum die Antwort entscheidet.

6. TOP 5
Die fünf Lücken, deren Schließung die Kausalitätskette am stärksten verbessert, mit einem Satz, was sich dann ändert.

Regeln: Nur Quelleninhalt, jede Aussage mit Fundstelle oder [BELEG FEHLT]. Keine Wiederholung der Matrix. Kein Vorspann.
