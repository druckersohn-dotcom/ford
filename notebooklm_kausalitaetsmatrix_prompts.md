# Kausalitätsmatrix § 612a BGB und Überarbeitung des Zieldokuments: Prompt-Kette für NotebookLM

Verfahren Matt ./. octeo MULTISERVICES GmbH, ArbG Duisburg, 4 Ca 1222/26.

Zweck der Kette: Das Dokument "Matt octeo schreiben und akte 4ca1222 26" (im Folgenden: ZIELDOKUMENT) wird verbessert. Jede Behauptung darin bekommt einen Beleg aus dem Zieldokument selbst oder aus einer anderen Quelle des Notebooks. Die Kausalitätsmatrix ist das Werkzeug dafür, nicht das Endprodukt.

## Anleitung

Voraussetzungen vor Prompt 1:
- Chat-Konfiguration v3 ist aktiv.
- Alle Quellen im Notebook sind angehakt. Vor jedem Prompt prüfen, NotebookLM merkt sich Abwahlen.
- Das Zieldokument liegt als eigene Quelle vor. Enthält es eingebettete Anlagen (Bilder, Scans), müssen diese eine Textebene haben, sonst sieht NotebookLM sie nicht.
- Weicht der Quellenname im Notebook von "Matt octeo schreiben und akte 4ca1222 26" ab, den Namen in allen Prompts im Block ZIELDOKUMENT anpassen.

Reihenfolge:
1. Prompt 1 im Chat. Antwort als Notiz speichern, Titel: "INVENTAR".
2. Prompt 2 im Chat. Antwort als Notiz speichern, Titel: "EREIGNISSE". Bricht die Antwort ab: "Setze bei Tabelle [Buchstabe] Zeile [Nr] fort, keine Wiederholung." senden.
3. Notizen INVENTAR und EREIGNISSE über "In Quelle umwandeln" zu Quellen machen.
4. Prompt 3 als eigener Bericht im Studio (Variante 3a). Fehlen im Bericht Fundstellen, stattdessen Variante 3b im Chat. Ergebnis als Notiz "MATRIX" speichern und in eine Quelle umwandeln.
5. Prompt 4 im Chat. Ergebnis als Notiz "LÜCKEN" speichern und in eine Quelle umwandeln.
6. Prompt 5 im Chat, abschnittsweise. Ergebnis ist die überarbeitete Fassung des Zieldokuments für den Anwalt.
7. Nach jeder neuen Anlage im Notebook: Prompt 4 und Prompt 5 erneut.

Jeder Prompt liegt unter 10.000 Zeichen.

Block ZIELDOKUMENT (steht in jedem Prompt, muss unverändert bleiben):

ZIELDOKUMENT: Die Quelle mit dem Namen "Matt octeo schreiben und akte 4ca1222 26" oder dem am nächsten liegenden Namen; es ist die Quelle, die das Schreiben des Klägers an octeo und die Aktenzusammenstellung zu 4 Ca 1222/26 enthält. Beginne die Antwort mit einer Zeile "ZIELDOKUMENT: [exakter Quellenname], [Seitenzahl] Seiten". Findest du keine passende Quelle, schreibe "ZIELDOKUMENT NICHT GEFUNDEN", nenne die drei Quellen mit der größten Ähnlichkeit und brich ab.

---

## PROMPT 1: INVENTAR

ZIELDOKUMENT: Die Quelle mit dem Namen "Matt octeo schreiben und akte 4ca1222 26" oder dem am nächsten liegenden Namen; es ist die Quelle, die das Schreiben des Klägers an octeo und die Aktenzusammenstellung zu 4 Ca 1222/26 enthält. Beginne die Antwort mit einer Zeile "ZIELDOKUMENT: [exakter Quellenname], [Seitenzahl] Seiten". Findest du keine passende Quelle, schreibe "ZIELDOKUMENT NICHT GEFUNDEN", nenne die drei Quellen mit der größten Ähnlichkeit und brich ab.

Aufgabe: Inventar aller Quellen dieses Notebooks und Gliederung des Zieldokuments. Noch keine Bewertung, keine Zusammenfassung, keine Auslassung.

TEIL 1: GLIEDERUNG DES ZIELDOKUMENTS
Gehe das Zieldokument von der ersten bis zur letzten Seite durch. Tabelle, eine Zeile je Abschnitt oder enthaltenem Dokument:
Nr | Seite von bis | Überschrift oder erste Zeile | Art (Schreiben, Sachverhaltsdarstellung, rechtliche Bewertung, Forderung, eingebettete Anlage, E-Mail, Protokoll, Abrechnung, Tabelle, sonstiges) | Datum | Enthaltene Tatsachenbehauptungen (Stichwort mit Datum) | Belegt innerhalb des Zieldokuments (Seite der Anlage) oder "kein Beleg im Dokument"

Danach TABELLE Z: alle Tatsachenbehauptungen des Zieldokuments einzeln:
Z-Nr | Seite | Behauptung (kurz, mit Datum) | Beleg im Zieldokument (Seite) oder "fehlt" | Beleg in anderer Quelle (Quellenname, Seite) oder "fehlt" | Status: BELEGT INTERN, BELEGT EXTERN, BELEGT BEIDES, UNBELEGT

TEIL 2: ALLE QUELLEN
Gehe jede Quelle einzeln durch, in der Reihenfolge der Quellenliste, das Zieldokument eingeschlossen. Enthält eine Quelle mehrere Dokumente (Anlagenkonvolut, E-Mail-Verlauf, mehrere Abrechnungen), bekommt jedes enthaltene Dokument eine eigene Zeile mit Unternummer (3.1, 3.2).

Tabelle, eine Zeile je Dokument:
Nr | Quellenname exakt wie im Notebook | Dokumentart | Aussteller/Absender | Empfänger | Datum | Zeitraum, den es betrifft | Vorgänge, die es belegt (Stichwort mit Datum, Seite) | Relevanz | Stützt welche Z-Nr aus Tabelle Z | Umfang (Seiten)

Spalte Relevanz, Mehrfachnennung möglich:
R = Rechtsausübung des Klägers (Lohn- oder Tarifforderung, Widerspruch, Gewerkschaftsbeitritt, Beschwerde nach §§ 84, 85 BetrVG, Anwaltsschreiben, Klage, Verweigerung einer Weisung, Auskunftsverlangen)
M = Maßnahme von octeo gegen den Kläger (Entzug von Objekt, Stunden, Diensten, Schicht; Versetzung; Abmahnung; Kontrolle; Kündigung; Nichtzahlung)
K = Kenntnis oder Entscheidung: wer bei octeo wann von einer Rechtsausübung wusste oder eine Maßnahme anordnete
G = Grund oder Entlastung: Stelle, die octeo als sachlichen Grund, Pflichtverstoß des Klägers oder vorbestehende Planung zitieren könnte
V = Vergleichspersonen
E = Entgelt: Stundensatz, Stunden, Zulagen, Zuschläge, Abrechnung
B = Betriebsrat
0 = keine Relevanz

Nach den Tabellen:
1. Gesamtzahl der Quellen und der Zeilen. Abweichung: Grund je Fall.
2. Quellen, die nicht oder nur teilweise lesbar waren (Scan ohne Text, Bild, abgeschnitten), mit Angabe, was fehlt; eingebettete Anlagen im Zieldokument gesondert.
3. Dokumente ohne erkennbares Datum.
4. Namen von octeo-Mitarbeitern mit Funktion: Name | Funktion | Quelle.
5. Zählung aus Tabelle Z: wie viele Behauptungen BELEGT INTERN, BELEGT EXTERN, BELEGT BEIDES, UNBELEGT.

Regeln:
- Nur aus den Quellen, nichts aus dem Chatverlauf oder Rechtswissen ergänzen.
- Keine Quelle als "ähnlich wie oben" zusammenfassen.
- Unsichere Zuordnung mit [PRÜFEN] markieren.
- Reicht die Antwortlänge nicht: "FORTSETZUNG FOLGT" und auf Aufforderung fortsetzen.

Selbsttest: Steht jede Quelle in Teil 2? Hat jede Behauptung des Zieldokuments eine Z-Nr?

---

## PROMPT 2: EREIGNISEXTRAKTION

ZIELDOKUMENT: Die Quelle mit dem Namen "Matt octeo schreiben und akte 4ca1222 26" oder dem am nächsten liegenden Namen; es ist die Quelle, die das Schreiben des Klägers an octeo und die Aktenzusammenstellung zu 4 Ca 1222/26 enthält. Beginne die Antwort mit einer Zeile "ZIELDOKUMENT: [exakter Quellenname], [Seitenzahl] Seiten". Findest du keine passende Quelle, schreibe "ZIELDOKUMENT NICHT GEFUNDEN", nenne die drei Quellen mit der größten Ähnlichkeit und brich ab.

Grundlage: Quelle INVENTAR, das Zieldokument und alle Originalquellen. Aufgabe: alle Ereignisse mit Bezug zu § 612a BGB in fünf Tabellen erfassen. Noch keine Kausalitätswertung.

Vorgehen: Gehe das Inventar Zeile für Zeile durch. Jede Zeile mit Relevanz R, M, K, G, V oder B muss in mindestens einer der Tabellen A bis E mit Fundstelle auftauchen. Ein Vorgang, der in mehreren Quellen belegt ist, bekommt eine Zeile mit allen Fundstellen. Jede Zeile trägt zusätzlich die Spalte "Im Zieldokument": Seite, auf der das Zieldokument den Vorgang behauptet, plus Z-Nr aus INVENTAR, oder "fehlt im Zieldokument".

TABELLE A: Rechtsausübungen des Klägers
Nr | Datum | Handlung | Form (mündlich, Brief, E-Mail, Fax, über Anwalt, Klage) | Adressat bei octeo (Name, Funktion) | Zugang oder Kenntnisnahme belegt durch (Quelle, Seite) | Weitere Personen bei octeo, die davon erfuhren (Name, Datum, Beleg) | Reaktion von octeo mit Datum und Beleg | Im Zieldokument | Lücke
Mindestens: Tarifforderung 07.11.2025, Gewerkschaftsbeitritt (und ob octeo davon wusste), Lohnwiderspruch 31.01.2026, Zahlungsaufforderung 23.02.2026, Fax 12.03.2026, Beschwerden nach §§ 84, 85 BetrVG, Klageerhebung, jede weitere belegte Geltendmachung, Verweigerung oder Beanstandung einer Weisung, Auskunftsverlangen.

TABELLE B: Maßnahmen von octeo gegen den Kläger
Nr | Datum der Anordnung | Zugang beim Kläger | Wirksamwerden | Maßnahme | Angeordnet durch (Name, Funktion) | Umgesetzt durch | Form | Begründung von octeo wörtlich aus der Quelle oder "keine Begründung in den Quellen" | Erstmals dokumentiert am (früheste Quelle, die die Maßnahme oder ihre Planung erwähnt) | Wirkung auf den Kläger (Stunden pro Monat, Zuschläge, Arbeitsort, Arbeitszeit, Entgelt in EUR) | Betriebsrat beteiligt (ja, nein, unbekannt; Beleg) | Quellen | Im Zieldokument | Lücke
Mindestens: Drohung 07.11.2025, Entzug Sporthalle Hitzestraße 06.02.2026, Versetzung des Arbeitsorts, Wechsel in die Spätschicht, Entzug der Wochenenddienste, Kürzung oder Verschiebung von Stunden, Nichtzahlung oder Kürzung von Entgelt, Abmahnungen, Inspektion 16./17.06.2026, Fotoaufnahmen, Beschattung oder GPS-Ortung, Vernichtung der Original-Stundenzettel, fristlose Kündigung 19.06.2026, Vorgänge nach der Kündigung, jede weitere belegte Schlechterstellung.

TABELLE C: Kenntnis- und Entscheiderkette
Person bei octeo | Funktion | Wusste von welcher Rechtsausübung (Nr aus A) seit wann (Beleg) | Hat welche Maßnahme (Nr aus B) angeordnet oder umgesetzt (Beleg) | Äußerungen zum Motiv, wörtlich mit Quelle | Im Zieldokument

TABELLE D: Entlastungsstellen
Jede Stelle, die octeo zu seinen Gunsten zitieren kann, auch aus dem Zieldokument selbst: Nr | Quelle, Seite | Inhalt wörtlich | Betrifft Maßnahme (Nr aus B) | Entstehungsdatum des Dokuments | Vor oder nach dem 31.01.2026 | Vor oder nach dem 07.11.2025 | Was octeo daraus machen wird (ein Satz)
Hierzu: Auslastung, Belegungspläne, Umstrukturierung, Kundenwünsche, Pflichtverstöße oder Beanstandungen gegen den Kläger, Krankheitszeiten, Versetzungen vor dem 07.11.2025, Vergleichsangebote, Äußerungen des Klägers, die gegen ihn verwendet werden können, überschießende oder unbelegte Formulierungen im Zieldokument.

TABELLE E: Vergleichspersonen und bisherige Praxis
Person oder Gruppe | Tätigkeit und Objekt | Was ihr zugewiesen, belassen oder entzogen wurde, mit Datum | Hat sie Ansprüche geltend gemacht | Quelle | Bedeutung für den Vergleich (ein Satz) | Im Zieldokument
Zusätzlich: bisherige Praxis gegenüber dem Kläger vor dem 07.11.2025 (Objekte, Schichten, Wochenenddienste, Stunden pro Monat) mit Quelle.

Regeln:
- Nur Quelleninhalt. Fehlendes: [BELEG FEHLT] in der Spalte Lücke, mit dem Dokument, das den Beleg liefern würde ("Dienstplan KW 06/2026", "Weisungs-E-Mail 06.02.2026", "Anhörung Betriebsrat § 102 BetrVG").
- Daten als TT.MM.JJJJ; unklar: [DATUM] plus Eingrenzung.
- Wörtliche Zitate in Anführungszeichen mit Seite.
- Keine Zeile ohne Quelle.
- Widersprüche zwischen Quellen, auch zwischen Zieldokument und Anlage: beide Angaben nennen, [WIDERSPRUCH].

Abschluss: 1. Inventar-Zeilen mit Relevanz R, M, K, G, V oder B, die in keiner Tabelle vorkommen, mit Grund. 2. Vorgänge aus A bis E, die im Zieldokument fehlen, als Liste mit Nr. 3. Behauptungen des Zieldokuments (Z-Nr), zu denen die Tabellen keinen Beleg gefunden haben. Danach "FORTSETZUNG FOLGT", falls nötig.

---

## PROMPT 3a: KAUSALITÄTSMATRIX (Studio, eigener Bericht)

ZIELDOKUMENT: Die Quelle mit dem Namen "Matt octeo schreiben und akte 4ca1222 26" oder dem am nächsten liegenden Namen; es ist die Quelle, die das Schreiben des Klägers an octeo und die Aktenzusammenstellung zu 4 Ca 1222/26 enthält. Beginne den Bericht mit einer Zeile "ZIELDOKUMENT: [exakter Quellenname], [Seitenzahl] Seiten". Findest du keine passende Quelle, schreibe "ZIELDOKUMENT NICHT GEFUNDEN", nenne die drei Quellen mit der größten Ähnlichkeit und brich ab.

Rolle: Juristischer Zuarbeiter auf Klägerseite im Verfahren Matt ./. octeo MULTISERVICES GmbH (ArbG Duisburg, 4 Ca 1222/26). Adressat ist der Anwalt des Klägers; der Bericht dient der Überarbeitung des Zieldokuments und muss ohne Umschreiben übernommen werden können. Dritte Person ("der Kläger", "die Beklagte"), keine Anrede, kein Vorspann, kein Hinweis auf KI oder fehlende Rechtsberatung. Parteiisch in der Wertung, präzise in der Subsumtion. Schwache Punkte einmal benennen, [SCHWACH].

Quellenregeln: Jede Tatsache ausschließlich aus den Quellen, mit Fundstelle (Quellenname, Seite). Grundlage sind INVENTAR und EREIGNISSE, gegengeprüft am Zieldokument und an den Originalquellen. Belege aus dem Zieldokument selbst und aus anderen Quellen gleichwertig verwenden, immer beide nennen, wenn beide vorhanden. Fehlt ein Beleg: [BELEG FEHLT] mit fehlendem Dokument. Nichts ergänzen, nichts glätten. Normen mit Absatz; Aktenzeichen nur, wenn sicher, sonst "(Az. prüfen)".

Rechtlicher Rahmen: § 612a BGB. Tatbestand: (1) zulässige Rechtsausübung, (2) Benachteiligung, (3) Kausalität; die Rechtsausübung muss tragender Beweggrund sein, ein bloßer äußerer Anlass genügt nicht (BAG 23.04.2009 – 6 AZR 189/08, Az. prüfen). Beweislast für alle drei Merkmale beim Kläger; keine Beweislastumkehr. Beweis über Indizien in der Gesamtwürdigung nach § 286 Abs. 1 ZPO. Die Beklagte trifft die sekundäre Darlegungslast für ihre Motive (§ 138 Abs. 2 ZPO); nicht substanziiert Bestrittenes gilt als zugestanden (§ 138 Abs. 3 ZPO). Nie schreiben, die Beklagte müsse die fehlende Kausalität beweisen.

Aufbau:

1. ÜBERSICHTSMATRIX
Zeilen: alle Rechtsausübungen (Tabelle A aus EREIGNISSE). Spalten: alle Maßnahmen (Tabelle B). Zelle: Abstand in Tagen von der Rechtsausübung bis zur Anordnung, dahinter Indizstärke: +++ stark, ++ mittel, + schwach, 0 kein Indiz, X zeitlich ausgeschlossen (Maßnahme vor der Rechtsausübung oder vor Kenntnis des Entscheiders). Keine Zelle leer.

2. ZELLBLÄTTER
Für jedes Paar ab Stärke + ein Block mit genau diesen Punkten:
a) Abstand in Tagen; Datum der Rechtsausübung, der Kenntnis des Entscheiders, der Anordnung, je mit Fundstelle.
b) Kenntnis: Kannte die anordnende Person die Rechtsausübung vor der Anordnung? Beleg oder [BELEG FEHLT].
c) Sachlicher Grund: vor der Rechtsausübung dokumentiert? Ja mit Fundstelle und Datum, oder nein. Begründung der Beklagten wörtlich oder "keine Begründung dokumentiert".
d) Abweichung von bisheriger Praxis und Vergleichspersonen (Tabelle E).
e) Muster: weitere Maßnahmen binnen 30 Tagen nach derselben Rechtsausübung, Nr aus B.
f) Betriebsrat beteiligt: ja, nein, unbekannt; Beleg.
g) Motivbelege: wörtliche Äußerungen der Beklagten (Tabelle C).
h) Entlastung: alles aus Tabelle D zu dieser Zelle, mit Entstehungsdatum und Entgegnung in je einem Satz.
i) Indizstärke mit zwei Sätzen Begründung.
j) Beweisantritte: Urkunde (Quellenname, bei Anlagen im Zieldokument dessen Seite), Zeuge (Name, Funktion, Beweisthema), Parteivernehmung, Vorlageantrag § 142 ZPO (Dienstpläne, Belegungsplan, Systemprotokolle, Weisungs-E-Mail, Betriebsratsanhörung).
k) Im Zieldokument: Seite und Z-Nr, auf der das Zieldokument diese Verbindung bereits vorträgt, oder "fehlt"; was dort ergänzt, belegt oder gestrichen werden muss.
l) Lücken: [BELEG FEHLT] mit Dokument.

3. GESAMTWÜRDIGUNG
Indizienkette in der Reihenfolge ihrer Stärke als Schriftsatzvortrag, getrennt für Sporthalle, Folgemaßnahmen, Kündigung 19.06.2026. Formel: "Die Indizien tragen den Vollbeweis, solange die Beklagte keinen dokumentierten, vor dem 31.01.2026 angelegten sachlichen Grund darlegt."

4. DIE SCHWÄCHSTEN STELLEN
Die drei Zellen, bei denen die Beklagte am ehesten einen sachlichen Grund belegen kann, [SCHWACH], mit dem Dokument, das die Lage drehen würde.

5. VORTRAG DER BEKLAGTEN AUS DENSELBEN QUELLEN
Mit Fundstelle und Entgegnung; Formulierungen des Zieldokuments, die die Beklagte gegen den Kläger wenden kann, gesondert.

6. ÄNDERUNGSBEDARF IM ZIELDOKUMENT
Tabelle: Seite | Z-Nr | Jetziger Text (kurz) | Problem (unbelegt, falscher Beleg, zu scharf, zu schwach, fehlt ganz, Widerspruch zur Anlage) | Vorschlag (neuer Text oder einzufügender Beleg mit Quelle und Seite) | Betroffene Zelle der Matrix

7. LÜCKENLISTE
Alle [BELEG FEHLT], sortiert nach Wirkung auf die Kausalität, mit fehlendem Dokument und Beschaffungsweg (Vorlageantrag § 142 ZPO, Auskunft, Zeuge, eigener Bestand).

Stil: Tabellen für Matrix, Änderungsbedarf und Lückenliste. Zahlen statt Adjektive. Keine Hedging-Ketten. Jede Behauptung mit Fundstelle oder Marker.

---

## PROMPT 3b: KAUSALITÄTSMATRIX (Chat, Fallback)

ZIELDOKUMENT: Die Quelle mit dem Namen "Matt octeo schreiben und akte 4ca1222 26" oder dem am nächsten liegenden Namen; es ist die Quelle, die das Schreiben des Klägers an octeo und die Aktenzusammenstellung zu 4 Ca 1222/26 enthält. Beginne die Antwort mit einer Zeile "ZIELDOKUMENT: [exakter Quellenname], [Seitenzahl] Seiten". Findest du keine passende Quelle, schreibe "ZIELDOKUMENT NICHT GEFUNDEN", nenne die drei Quellen mit der größten Ähnlichkeit und brich ab.

Grundlage: INVENTAR und EREIGNISSE, gegengeprüft am Zieldokument und den Originalquellen. Belege aus dem Zieldokument und aus anderen Quellen gleichwertig, beide nennen, wenn vorhanden. Beweislast für § 612a BGB beim Kläger; Indizien in der Gesamtwürdigung nach § 286 Abs. 1 ZPO, sekundäre Darlegungslast der Beklagten nach § 138 Abs. 2 ZPO. Keine Beweislastumkehr behaupten.

Liefere in dieser Reihenfolge, mit Fundstellen:

1. ÜBERSICHTSMATRIX: Zeilen = Rechtsausübungen (Tabelle A), Spalten = Maßnahmen (Tabelle B). Zelle = Abstand in Tagen bis zur Anordnung plus Indizstärke (+++ stark, ++ mittel, + schwach, 0 keines, X zeitlich ausgeschlossen). Keine Zelle leer.

2. ZELLBLÄTTER für jedes Paar ab Stärke +, je mit: a) Abstand in Tagen und drei Daten (Rechtsausübung, Kenntnis des Entscheiders, Anordnung); b) Kenntnis des Entscheiders mit Beleg; c) sachlicher Grund vor der Rechtsausübung dokumentiert: ja mit Fundstelle und Datum, oder nein; Begründung der Beklagten wörtlich oder "keine Begründung dokumentiert"; d) Abweichung von bisheriger Praxis und Vergleichspersonen; e) weitere Maßnahmen binnen 30 Tagen; f) Betriebsrat beteiligt; g) Motivbelege wörtlich; h) Entlastungsstellen aus Tabelle D mit Entstehungsdatum und Entgegnung; i) Indizstärke mit zwei Sätzen; j) Beweisantritte: Urkunde (bei Anlagen im Zieldokument dessen Seite), Zeuge mit Beweisthema, Parteivernehmung, Vorlageantrag § 142 ZPO; k) Im Zieldokument: Seite und Z-Nr oder "fehlt", und was dort zu ergänzen, zu belegen oder zu streichen ist; l) Lücken als [BELEG FEHLT] mit Dokument.

3. GESAMTWÜRDIGUNG als Schriftsatzvortrag, getrennt für Sporthalle, Folgemaßnahmen, Kündigung. Formel: "Die Indizien tragen den Vollbeweis, solange die Beklagte keinen dokumentierten, vor dem 31.01.2026 angelegten sachlichen Grund darlegt."

4. DIE DREI SCHWÄCHSTEN ZELLEN mit [SCHWACH] und dem Dokument, das die Lage drehen würde.

5. VORTRAG DER BEKLAGTEN aus denselben Quellen, mit Fundstelle und Entgegnung; Formulierungen des Zieldokuments, die sich gegen den Kläger wenden lassen, gesondert.

6. ÄNDERUNGSBEDARF IM ZIELDOKUMENT: Seite | Z-Nr | Jetziger Text | Problem (unbelegt, falscher Beleg, zu scharf, zu schwach, fehlt, Widerspruch zur Anlage) | Vorschlag mit Beleg (Quelle, Seite) | Zelle der Matrix.

7. LÜCKENLISTE nach Wirkung auf die Kausalität, mit Beschaffungsweg.

Antwort zu lang: erst 1 und 2 vollständig, dann "FORTSETZUNG FOLGT"; 3 bis 7 auf Aufforderung.

---

## PROMPT 4: VOLLSTÄNDIGKEITSKONTROLLE

ZIELDOKUMENT: Die Quelle mit dem Namen "Matt octeo schreiben und akte 4ca1222 26" oder dem am nächsten liegenden Namen; es ist die Quelle, die das Schreiben des Klägers an octeo und die Aktenzusammenstellung zu 4 Ca 1222/26 enthält. Beginne die Antwort mit einer Zeile "ZIELDOKUMENT: [exakter Quellenname], [Seitenzahl] Seiten". Findest du keine passende Quelle, schreibe "ZIELDOKUMENT NICHT GEFUNDEN", nenne die drei Quellen mit der größten Ähnlichkeit und brich ab.

Grundlage: INVENTAR, EREIGNISSE, MATRIX, das Zieldokument und alle Originalquellen. Aufgabe: prüfen, ob die Matrix alles aus dem Notebook verwertet und ob jede Behauptung des Zieldokuments einen Beleg hat.

1. ABGLEICH QUELLE GEGEN MATRIX
Tabelle: Nr aus INVENTAR | Quellenname | Relevanz | Zitiert in Zelle(n) der Matrix oder "nicht zitiert" | Falls nicht zitiert: Grund (irrelevant, übersehen, nur Entgelt) | Beitrag zur Kausalität (ein Satz mit Fundstelle)
Jede Quelle mit Relevanz R, M, K, G, V oder B, die "nicht zitiert" und nicht "irrelevant" ist, gilt als übersehen.

2. ABGLEICH ZIELDOKUMENT GEGEN QUELLEN
Tabelle über alle Z-Nr aus INVENTAR: Z-Nr | Seite | Behauptung | Beleg im Zieldokument (Seite) | Beleg in anderer Quelle (Name, Seite) | Status (BELEGT INTERN, BELEGT EXTERN, BELEGT BEIDES, UNBELEGT) | Stimmt die Behauptung mit dem Beleg überein (ja, Abweichung mit Angabe) | Zelle der Matrix
Danach: Vorgänge aus EREIGNISSE, die im Zieldokument fehlen, mit Angabe, in welchen Abschnitt sie gehören.

3. NACHTRAG
Für jede übersehene Quelle: Welche Zelle ändert sich, in welche Richtung, mit Fundstelle. Neue Zeile oder Spalte, falls die Quelle eine nicht erfasste Rechtsausübung oder Maßnahme belegt.

4. WIDERSPRÜCHE
Alle Stellen, an denen Quellen einander oder dem Zieldokument widersprechen (Daten, Stunden, Beträge, Namen, Reihenfolge): Quelle 1 mit Angabe | Quelle 2 mit Angabe | Zelle | Für den Kläger günstigere Version und Auflösung.

5. ERWARTBARE, ABER FEHLENDE DOKUMENTE
Prüfe mindestens: Weisung zum Entzug der Sporthalle in Textform; Dienst- und Belegungspläne vor und nach dem 06.02.2026; Zugangsnachweise für 31.01., 23.02., 12.03.2026; Anhörung des Betriebsrats nach § 102 Abs. 1 BetrVG; Beteiligung nach § 99 Abs. 1 BetrVG zu Versetzung und Schichtwechsel; Arbeitsvertrag mit Ausschlussklausel; Mitgliedsbestätigung IG BAU; Protokoll zur Inspektion 16./17.06.2026; Kündigungsschreiben mit Begründung; Antworten von octeo auf die Geltendmachungen; Zeiterfassung von octeo 01/2023 bis 06/2026.
Tabelle: Dokument | Wer hat es (Kläger, Beklagte, Betriebsrat, Dritte) | Zelle | Z-Nr im Zieldokument, die davon abhängt | Beschaffungsweg (eigener Bestand, Vorlageantrag § 142 ZPO, Auskunft, Zeuge, Betriebsrat) | Priorität 1 bis 3

6. RÜCKFRAGEN AN DEN ANWALT
Nummeriert. Nur Fragen, deren Antwort eine Zelle oder eine Z-Nr verändert, mit Angabe, welche.

7. TOP 5
Die fünf Lücken, deren Schließung die Kausalitätskette und das Zieldokument am stärksten verbessert, je ein Satz.

Regeln: Nur Quelleninhalt, jede Aussage mit Fundstelle oder [BELEG FEHLT]. Keine Wiederholung der Matrix. Kein Vorspann.

---

## PROMPT 5: ÜBERARBEITUNG DES ZIELDOKUMENTS

ZIELDOKUMENT: Die Quelle mit dem Namen "Matt octeo schreiben und akte 4ca1222 26" oder dem am nächsten liegenden Namen; es ist die Quelle, die das Schreiben des Klägers an octeo und die Aktenzusammenstellung zu 4 Ca 1222/26 enthält. Beginne die Antwort mit einer Zeile "ZIELDOKUMENT: [exakter Quellenname], [Seitenzahl] Seiten". Findest du keine passende Quelle, schreibe "ZIELDOKUMENT NICHT GEFUNDEN", nenne die drei Quellen mit der größten Ähnlichkeit und brich ab.

Grundlage: das Zieldokument, INVENTAR (Tabelle Z), EREIGNISSE, MATRIX, LÜCKEN und alle Originalquellen. Aufgabe: das Zieldokument Abschnitt für Abschnitt so überarbeiten, dass der Anwalt es ohne Umschreiben verwenden kann. Jede Tatsachenbehauptung bekommt einen Beleg aus dem Zieldokument selbst (Seite) oder aus einer anderen Quelle (Name, Seite), oder den Marker [BELEG FEHLT] mit dem fehlenden Dokument.

Arbeite Abschnitt für Abschnitt nach der Gliederung aus INVENTAR Teil 1. Liefere pro Abschnitt:

A. ÜBERARBEITETER TEXT
Vollständiger neuer Text des Abschnitts in Schriftsatzsprache, dritte Person ("der Kläger", "die Beklagte"). Nach jeder Tatsachenbehauptung in Klammern der Beleg: (Zieldokument S. x) oder (Quellenname, S. x) oder [BELEG FEHLT: Dokument]. Beweisantritte am Ende jedes Tatsachenblocks: "Beweis: Urkunde ..., Zeuge ..., Parteivernehmung, Vorlageantrag § 142 ZPO ...". Normen mit Absatz.

B. ÄNDERUNGSPROTOKOLL
Tabelle: Z-Nr | Alt (kurz) | Neu (kurz) | Art (Beleg ergänzt, Beleg korrigiert, Formulierung geschärft, Formulierung entschärft, gestrichen, neu aufgenommen) | Grund mit Fundstelle oder Zelle der Matrix
Gestrichen wird nur, was unbelegt ist und bleiben würde, oder was der Beklagten nützt (Tabelle D). Geschärft wird nur, was die Quellen tragen. Entschärft wird, was die Quellen nicht tragen; [SCHWACH] bleibt sichtbar.

C. NEU AUFGENOMMENE VORGÄNGE
Vorgänge aus EREIGNISSE, die das Zieldokument bisher nicht enthielt und die in diesen Abschnitt gehören, mit Beleg.

Reihenfolge der Abschnitte und Kausalitätsargument: Der Abschnitt zur Kausalität folgt der Indizienkette aus MATRIX, Abschnitt 3, mit der Formel "Die Indizien tragen den Vollbeweis, solange die Beklagte keinen dokumentierten, vor dem 31.01.2026 angelegten sachlichen Grund darlegt." Beweislast beim Kläger, sekundäre Darlegungslast der Beklagten (§ 138 Abs. 2 ZPO); keine Beweislastumkehr behaupten. Antizipierte Einwände der Beklagten aus MATRIX, Abschnitt 5, mit Entgegnung in den jeweiligen Abschnitt aufnehmen.

Bezifferung: Jede Forderung als Tabelle (Monat | Stunden | gezahlt €/h | geschuldet €/h | Differenz €/h | Differenz € brutto | Geltendmachung/Frist) mit Fundstelle je Zahl; fehlende Zahl als [BETRAG] oder [Stunden p. M.].

Regeln: Nur Quelleninhalt. Keine Floskeln, kein Vorspann, kein Hinweis auf KI. Zahlen statt Adjektive. Widersprüche zwischen Zieldokument und Anlage werden zugunsten der Anlage aufgelöst und im Änderungsprotokoll vermerkt.

Umfang: Bearbeite in dieser Antwort nur Abschnitt 1 bis [Nr] der Gliederung. Schließe mit "NÄCHSTER ABSCHNITT: [Nr]". Auf "weiter" folgt der nächste Abschnitt ohne Wiederholung. Nach dem letzten Abschnitt: Gesamtliste aller [BELEG FEHLT] und aller [SCHWACH] mit Seite, als Rückfragenliste an den Anwalt.
