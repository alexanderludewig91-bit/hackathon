# Hackathon Briefing: Föderale Antragsplattform

## Hintergrund

### Die Vision: „Einmal für Alle!"

Die Machbarkeitsstudie des IT-Planungsrats (Stand: Dezember 2025) beschreibt die Vision einer **zentralen, föderalen Antragsplattform** für Deutschland. Ziel ist es, Verwaltungsleistungen für alle Bürgerinnen und Bürger digital zugänglich zu machen – einfach, intuitiv und von überall erreichbar.

### Das Problem heute

- **69 Millionen potenzielle Nutzende** – aber nur ein Bruchteil nutzt digitale Verwaltungsangebote
- **Fragmentierte Landschaft**: Jede Kommune, jedes Bundesland entwickelt eigene Lösungen
- **Schlechte Auffindbarkeit**: Bürger wissen oft nicht, welche Leistungen ihnen zustehen oder wo sie diese beantragen können
- **Mangelnde Nutzerfreundlichkeit**: Die Usability entspricht nicht dem Standard, den Bürger aus dem Privatsektor (Amazon, Booking, etc.) gewohnt sind
- **Hohe Kosten**: Das Prinzip „Einer für Alle" (EfA) scheitert häufig an den Anbindungskosten für Kommunen

### Der Lösungsansatz

Die Studie schlägt eine Plattform vor, die:

1. **Zentralen Zugang** bietet – eine URL, ein Portal für alle Verwaltungsleistungen
2. **Ende-zu-Ende digitalisiert** – nicht nur das Formular, sondern den gesamten Prozess
3. **Bürgerorientiert** gestaltet ist – einfach, schnell, verständlich
4. **Föderale Strukturen** respektiert – Kommunen behalten ihre „Marke"
5. **Moderne Technologien** nutzt – Cloud, Low-Code, KI-Unterstützung

### Was Bürger sich wünschen

Laut der Studie erwarten Bürgerinnen und Bürger:

- **Einfachheit**: Weniger Bürokratie, verständliche Sprache
- **Geschwindigkeit**: Schnelle Bearbeitung, sofortiges Feedback
- **Transparenz**: Jederzeit wissen, wo der Antrag steht
- **Wiederverwendbarkeit**: Einmal hochgeladene Dokumente nicht erneut einreichen müssen (Once-Only-Prinzip)
- **Zugänglichkeit**: Von jedem Gerät, zu jeder Zeit

### Ergänzende Perspektive: FIM-Redaktionen / Leistungsbeschreibungen

Neben der Bürgerperspektive gibt es auch eine **Redaktionsperspektive** (z.B. FIM-Redaktionen), die Verwaltungsleistungen erstellt, abstimmt und veröffentlicht.

- **Problem heute (aus Redaktionssicht)**: Fragmentierte Redaktionssysteme mit eingeschränkter Interoperabilität (u.a. unterschiedliche XML-Standard-Versionen) sowie geringe Transparenz darüber, wie andere Länder Leistungen beschreiben; Abstimmungen über Ressort-/Organisationsgrenzen sind nur teilweise unterstützt.
- **Wünsche der FIM-Redaktionen**: Einfachere organisationsübergreifende Abstimmung, Transparenz über neue/geänderte Leistungen und Freigaben sowie optional **KI-Support** (Textvorschläge zur schnelleren Erstellung/Überarbeitung von Leistungstexten).

---

## Hackathon: Use Cases

Im Rahmen des Hackathons sollen **vereinfachte Prototypen** entwickelt werden, die zentrale Aspekte der föderalen Antragsplattform demonstrieren.

### Rahmenbedingungen

- ✅ Standalone-Lösung (keine Anbindung an Fachverfahren oder externe Systeme)
- ✅ Lokale Datenhaltung mit SQLite
- ✅ Fokus auf schnelle, sichtbare Ergebnisse
- ✅ AI-Coding-optimiert – klare, abgegrenzte Features

---

## Use Case 1: Intelligenter Antrags-Wizard

> *„Schritt für Schritt zum fertigen Antrag"*

### Beschreibung

Ein geführter, mehrstufiger Antragsprozess für eine beispielhafte Verwaltungsleistung (z.B. Wohngeld, Parkausweis, Hundesteueranmeldung). Der Wizard führt den Nutzer intuitiv durch alle erforderlichen Angaben und validiert Eingaben in Echtzeit.

### Hauptfunktionalitäten

- **Mehrstufiges Formular** mit visuellem Fortschrittsindikator
- **Dynamische Felder**: Je nach Eingabe werden relevante Folgefelder ein- oder ausgeblendet
- **Echtzeit-Validierung**: Sofortiges Feedback bei fehlerhaften oder unvollständigen Eingaben
- **Zusammenfassungsseite**: Übersicht aller Angaben vor dem Absenden
- **Bestätigungsseite**: Nach Absenden erhält der Nutzer eine Antragsnummer

### Wow-Faktoren

- Animierter Fortschrittsbalken
- Sanfte Übergänge zwischen den Schritten
- Konfetti-Animation bei erfolgreicher Einreichung 🎉
- Responsives Design für Desktop und Mobile

### Optionale KI-Erweiterung: Hilfe-Assistent

> *„Was bedeutet ‚Bruttoeinkommen'? Zählt Kindergeld dazu?"*

Ein **Chat-Widget** im Wizard, das kontextbezogene Hilfe bietet:

- Kleiner Chat-Button (z.B. unten rechts) während der Antragsstellung
- Nutzer tippt Frage ein → KI antwortet mit verständlicher Erklärung
- **Kontextbezogen**: Die KI weiß, in welchem Formularschritt sich der Nutzer befindet
- Erklärt Fachbegriffe, gibt Hinweise zu benötigten Dokumenten

**Beispiel-Interaktionen:**

| Nutzerfrage | KI-Antwort |
|-------------|------------|
| „Was ist Bruttoeinkommen?" | „Das Bruttoeinkommen ist Ihr Gehalt vor Abzug von Steuern und Sozialabgaben." |
| „Welche Dokumente brauche ich?" | „Für diesen Antrag benötigen Sie: Einkommensnachweis, Mietvertrag und Personalausweis." |

**Hinweis:** Der Wizard funktioniert auch ohne den Chatbot vollständig. Die KI ist ein „Nice-to-have", kein Muss.

---

## Use Case 2: Lebenslage-Finder

> *„Welche Leistungen stehen mir zu?"*

### Beschreibung

Ein interaktives Tool, das Bürgern hilft, passende Verwaltungsleistungen zu entdecken. Durch wenige, einfache Fragen zur persönlichen Lebenssituation ermittelt das System relevante Angebote.

### Hauptfunktionalitäten

- **Kurzer Fragebogen**: 5-7 verständliche Fragen (Ja/Nein oder Multiple-Choice)
- **Intelligentes Matching**: Regelbasierte Zuordnung von Leistungen basierend auf den Antworten
- **Leistungskatalog**: Übersicht verfügbarer Verwaltungsleistungen mit Beschreibung
- **Ergebnisanzeige**: Personalisierte Liste passender Leistungen
- **Direkte Weiterleitung**: „Jetzt beantragen"-Button führt zum entsprechenden Antrag

### Wow-Faktoren

- Quiz-artige, interaktive Oberfläche
- Animierte Ergebniskarten mit Einblendeffekt
- Counter-Animation: „X Leistungen für Sie gefunden!"
- Möglichkeit, Ergebnisse zu filtern oder zu sortieren

### Optionale KI-Erweiterung: Freitext-Eingabe

> *„Ich bin gerade umgezogen und habe zwei kleine Kinder…"*

Statt (oder zusätzlich zum) klassischen Fragebogen kann der Nutzer seine **Situation in eigenen Worten beschreiben**:

- Textfeld: „Beschreiben Sie Ihre Situation…"
- Nutzer schreibt 1-3 Sätze in natürlicher Sprache
- KI analysiert und identifiziert relevante Lebensereignisse und Bedarfe
- Ergebnis: Passende Verwaltungsleistungen werden vorgeschlagen

**Beispiel-Interaktionen:**

| Nutzereingabe | Vorgeschlagene Leistungen |
|---------------|---------------------------|
| „Ich bin alleinerziehend und habe meinen Job verloren." | Arbeitslosengeld, Kinderzuschlag, Wohngeld |
| „Wir haben ein Baby bekommen." | Elterngeld, Kindergeld, Kita-Gutschein |
| „Ich bin 67 und möchte in Rente gehen." | Rentenantrag, Grundsicherung im Alter |

**Hinweis:** Der klassische Fragebogen bleibt als Alternative erhalten. Nutzer können wählen:
- 📝 „Fragen beantworten" (klassisch)
- 💬 „Situation beschreiben" (KI-gestützt)

---

## Use Case 3: Antrags-Statustracker

> *„Wo ist mein Antrag?"*

### Beschreibung

Ein Tracking-Tool, mit dem Bürger den aktuellen Bearbeitungsstand ihrer Anträge verfolgen können – vergleichbar mit der Paketverfolgung bei Lieferdiensten.

### Hauptfunktionalitäten

- **Antragsnummer-Eingabe**: Einfaches Suchfeld zur Statusabfrage
- **Timeline-Darstellung**: Visualisierung aller Bearbeitungsschritte
- **Detailansicht**: Informationen zu jedem Schritt (Datum, Status, ggf. Hinweise)
- **Statusübersicht**: Aktueller Stand auf einen Blick (eingegangen, in Bearbeitung, erledigt)
- **Antragshistorie**: Liste aller eigenen Anträge (bei wiederholter Nutzung)

### Wow-Faktoren

- Elegante, vertikale Timeline-Komponente
- Farbcodierte Status-Badges (grün, gelb, rot)
- Geschätzte Restbearbeitungszeit
- Sanfte Animationen beim Laden der Statusdaten

---

## Use Case 4: Dokumenten-Tresor

> *„Einmal hochladen, überall nutzen"*

### Beschreibung

Ein persönlicher Dokumentenspeicher, in dem Bürger häufig benötigte Unterlagen (Personalausweis, Einkommensnachweise, Meldebescheinigung) ablegen und bei zukünftigen Anträgen wiederverwenden können.

### Hauptfunktionalitäten

- **Dokument-Upload**: Drag & Drop oder Dateiauswahl
- **Kategorisierung**: Zuordnung zu Dokumenttypen (Ausweisdokument, Nachweis, Bescheinigung, etc.)
- **Dokumentenübersicht**: Liste aller gespeicherten Dokumente mit Vorschau
- **Wiederverwendung**: Bei Antragsstellung Dokumente aus dem Tresor auswählen
- **Gültigkeitshinweis**: Anzeige, wenn Dokumente möglicherweise veraltet sind

### Wow-Faktoren

- Drag & Drop mit visuellem Feedback (Datei schwebt über Zielbereich)
- Dokumenttyp-spezifische Icons
- Vorschau-Thumbnails für hochgeladene Dokumente
- „X Dokumente gespeichert"-Badge im Header

---

## Use Case 5: Leistungsbeschreibung-Redaktion (FIM light)

> *„Leistungstexte erstellen, verbessern, vergleichen und freigeben"*

### Beschreibung

Ein vereinfachtes **Backoffice-Modul** für Verwaltungsmitarbeitende / (FIM-)Redaktionen, um Verwaltungsleistungen als Texte zu erstellen, zwischen Organisationen nachnutzbar zu machen und Änderungen transparent freizugeben – ohne Anbindung an externe Redaktionssysteme oder Fachverfahren.

### Hauptfunktionalitäten

- **Editor für Leistungstexte**: Leistung anlegen und bearbeiten (z.B. Titel, Kurzbeschreibung, Voraussetzungen, Unterlagen, Ablauf)
- **Status & Freigabe-Workflow**: Entwurf → in Prüfung → freigegeben (einfacher „Freigeben“-Button)
- **Änderungsverlauf light**: „Was hat sich geändert?“ (z.B. Vergleich der aktuellen Version zur vorherigen)
- **Vergleich / Nachnutzung**: „Ähnliche Leistung aus anderem Land ansehen“ (Mock-Daten reichen)
- **Transparenz-Board**: Liste „neu / aktualisiert / freigegeben“ für schnelle Übersicht

### Wow-Faktoren

- Diff-Ansicht wie bei Git (rot/grün) für Änderungen an Texten
- Visuelle Statusleiste für den Freigabeprozess
- Schnelles „Review“-Gefühl durch klare, reduzierte Oberfläche
- Dashboard-Kachel „Diese Woche geändert“ (kleine Kennzahlen reichen)

### Optionale KI-Erweiterung: Textvorschläge & Checks

> *„Formuliere diesen Abschnitt verständlicher“ / „Was fehlt noch?“*

KI als punktuelle Unterstützung im Redaktionsprozess:

- Button **„Text verbessern“** (Klartext, kürzer, aktiver Stil)
- Button **„Textvorschläge“** (alternativen Formulierungen / Varianten)
- Optional: **Konsistenz-Check** (z.B. Unterlagen erwähnt, aber nicht gelistet; unklare Begriffe)

**Hinweis:** Das Backoffice ist optional. Es kann unabhängig vom Bürgerportal gebaut werden oder als „Admin-Modus“ in derselben App existieren.

---

## Optionaler Baustein: Rollen-/Persona-Auswahl (simuliert)

> *„Willkommen zurück, Max Mustermann!“ / „Redaktionsmodus aktiv“*

### Warum relevant?

Viele der oben genannten Use Cases setzen eine **Nutzeridentität bzw. Rolle** voraus:

- **Bürgerportal**:
  - **Meine Anträge** – Welche Anträge gehören zu mir?
  - **Dokumenten-Tresor** – Wessen Dokumente sind das?
  - **Statusverfolgung** – Anträge einer Person zuordnen
- **Backoffice / Redaktion (FIM light)**:
  - **Leistungstexte bearbeiten** – Wer darf Inhalte ändern?
  - **Freigaben/Review** – Wer darf veröffentlichen?
  - **Transparenz** – Welche Änderungen wurden von wem freigegeben?

Ohne eine Form der Rollen-/Persona-Auswahl fehlt das realistische Benutzererlebnis (Bürgerperspektive und/oder Verwaltungsperspektive). Da eine echte Authentifizierung (mit Passwort-Handling, Sicherheit, etc.) für den Hackathon zu aufwendig wäre, empfehlen wir eine **vereinfachte Simulation**.

### Mögliche Umsetzungsvarianten

#### Variante A: Demo-Modus

- Button auf der Startseite: **„Als Testnutzer anmelden"**
- Ein Klick → Nutzer ist sofort als „Max Mustermann" eingeloggt
- Keine Eingabefelder, keine Passwörter
- Schnellste Variante für Prototypen

#### Variante B: Pseudo-Login

- Einfaches Formular mit **nur einem Feld: Name**
- Nutzer gibt einen beliebigen Namen ein
- System merkt sich den Namen für die aktuelle Session
- Ermöglicht personalisierte Begrüßung und Zuordnung

#### Variante C: Persona-Auswahl

- Dropdown oder Kacheln mit **vordefinierten Test-Personas** (gern nach Rollen gruppiert):
  - **Bürger-Personas**:
    - Max Mustermann (hat bereits Anträge gestellt)
    - Erika Musterfrau (Neunutzerin, keine Anträge)
    - Familie Schmidt (mehrere Personen im Haushalt)
  - **Redaktion/Admin-Personas** (optional, wenn Backoffice-UC umgesetzt wird):
    - FIM-Redaktion Bund (darf freigeben)
    - Landesredaktion (darf Entwürfe erstellen)
    - Reviewer/Prüfung (darf kommentieren und prüfen)
- Zeigt verschiedene Zustände und Szenarien (Bürgerportal und/oder Backoffice)
- Gut geeignet für Demos und Präsentationen

#### Variante D: Rollen-Switch (Bürger ↔ Redaktion)

- Umschalter/Dropdown in der UI (z.B. oben rechts): **„Rolle wechseln“**
- Wechselt die sichtbaren Bereiche (Bürgerportal vs. Backoffice) und ggf. die Persona
- Besonders hilfreich, wenn beide Module in einer Demo gezeigt werden sollen

### Hinweis

Die Wahl der Variante bleibt den Teilnehmenden überlassen. Je nach gewähltem Use Case kann auch komplett auf Rollen/Personas verzichtet werden – allerdings wirkt die Anwendung dann weniger wie eine echte Plattform mit „Meine…“-Bereichen bzw. Backoffice-Freigaben.

---

## Hinweise für Teilnehmende

- Die **technische Umsetzung** (Datenbankschema, API-Design, Frontend-Architektur) ist Teil der Hackathon-Aufgabe
- Es gibt **keine vorgegebene „richtige" Lösung** – Kreativität ist erwünscht!
- **Fokus auf Benutzererlebnis**: Eine einfache Lösung mit gutem UX ist wertvoller als eine komplexe Lösung mit schlechter Bedienbarkeit
- **Mockdaten sind erlaubt**: Für den Prototyp müssen keine echten Verwaltungsleistungen abgebildet werden

