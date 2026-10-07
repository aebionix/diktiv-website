# AI-Handover diktiv-website

Einstieg für jede neue Session. Stand 08.10.2026, geprüft an `main` (Merge-Commit `3f136c1`) und
am Live-Server.

## 1. Ziel und aktueller Stand

Öffentliche Website der Windows-Diktier-App Diktiv unter **https://diktiv.com**. Statische
HTML-Seiten ohne Build, ohne Framework, ohne externe Skripte. Beschrieben wird nur die
**Gratis-Version** (Entscheid Michael 07.10.2026, Premium wird nicht beworben).

Stand 08.10.2026: 8 Seiten live, jede Datei per `curl` und `cmp` byte-gleich mit `main` geprüft.
Keine offenen GitHub-Aufgaben in `aebionix/diktiv-website`.

| Seite | Deutsch | Englisch |
|---|---|---|
| Start | `site/index.html` | `site/index-en.html` |
| Funktionen | `site/funktionen.html` | `site/features.html` |
| Geschichte | `site/entstehung.html` | `site/story.html` |
| Datenschutz | `site/datenschutz.html` | `site/privacy.html` |

## 2. Abgeschlossene Arbeiten

- 07.10.2026: Datenschutzerklärung DE/EN live, URL im Microsoft Partner Center eingetragen.
- 07.10.2026: Funktionsseite im Bento-Raster mit allen Gratis-Funktionen (Aufgaben 1 bis 19, 39, 40).
- 07.10.2026: Englische Start- und Funktionsseite mit Sprachumschalter und hreflang (Aufgabe 42).
- 07./08.10.2026: Pille nach App-Stand, Kreuz entspricht Esc, Knöpfe und «⋯»-Menü der Pille.
- 08.10.2026: Seite «Wie Diktiv entstand» DE/EN aus dem Interview mit Michael, Sätze «Entstanden,
  weil …» auf den Funktionsseiten, Kachel mit allen Gratis-Verlaufsfunktionen (Aufgaben 45, 46, 48).

## 3. Relevante Dateien

- `site/` ist die Website. Alles darin wird 1:1 nach Hostpoint `www/diktiv.com` hochgeladen.
- `site/bilder/*.webp` sind Bildschirmfotos der App.
- `site/funktionen.html` und `site/features.html` enthalten CSS und Skript inline (Countdown der
  Pille, Transkription, Regler der interaktiven Pille).
- Quelle für Inhalte ist die App in `C:/Users/mike/source/repos/diktiv-next` (Forgejo
  `xonex/Diktiv`), dort `src/Diktiv.Core/Localization/Strings*.resx` für Beschriftungen und
  `docs/marketing/2026-10-07-interview-entstehung.md` für die Geschichte.

## 4. Architekturentscheide

- **Statisches HTML statt Generator.** Acht Seiten rechtfertigen keinen Build. Gemeinsames CSS ist
  pro Seite kopiert, bewusst in Kauf genommen.
- **Hosting bei Hostpoint (Schweiz)**, nicht GitHub Pages. Swiss First. Ein Push auf `main`
  veröffentlicht nichts, der Upload ist ein eigener Schritt.
- **Nur Gratis-Funktionen.** Jede Aussage ist am Code von diktiv-next geprüft, Premium- und
  KI-Funktionen bleiben draussen (auch «Veredelt», «Original einfügen», Titelvorschläge).
- **Beschriftungen wie in der App.** Regler und Knöpfe heissen exakt wie in den resx-Dateien,
  Englisch aus `Strings.resx`.
- **Pille als HTML/CSS nachgebaut**, keine Videos. Masse aus `FloatingWidget.axaml(.cs)`
  (150 px bei Aufnahme und Transkription, Zeit mittig, am Schluss ein Haken).
- **Geschichte ohne Konkurrenzname, Foto, Länder, Zukunftsversprechen** (Michael 08.10.2026).
  Statt «100 % offline» steht «funktioniert ohne Internet, ausser beim Dazuladen von Modellen».

## 5. Bauen, Testen, Veröffentlichen

- Lokal ansehen: beliebiger statischer Server auf `site/` (verwendet: Port 8931).
- Prüfen vor dem Upload: Desktop 1280 px ohne Lücken im Raster, Handy 375 px ohne seitlichen
  Überlauf (`document.documentElement.scrollWidth`), alle internen Links zeigen auf vorhandene Dateien.
- Veröffentlichen erst nach Michaels «veröffentlichen». Upload im Hostpoint-Dateimanager
  (`https://admin.hostpoint.ch/customer/Filemanager/FileUpload?what=www%2Fdiktiv%2Ecom`, Skill
  `my-hostpoint`), danach jede Datei mit `curl` gegen die lokale Fassung vergleichen.

## 6. Offene Punkte

- Keine offenen Aufgaben (08.10.2026).
- In der App gemeldet: KI-Pfeil im Gratis-Verlauf (diktiv-next intern #272), fehlende englische
  Übersetzung des Tooltips der geteilten Verlaufsansicht (intern #289). Die Website beschreibt
  bereits das Zielverhalten.
- Die Pille auf der Website entspricht dem App-Branch `feat/fortschritt-fuellung-274`. Bis er in
  diktiv-next ausgeliefert ist, sieht die veröffentlichte App leicht anders aus.

## 7. Fallstricke

- **Live ist nur `site/`.** Die alte Single-Page aus der Voxly-Zeit im Wurzelordner (`index.html`,
  `favicon.svg`) wurde am 08.10.2026 gelöscht und steht nur noch in der Git-History.
- Chrome-Upload liest nur aus erlaubten Ordnern. Dateien vorher in den Scratchpad der Session kopieren.
- Aus einer Worktree-Session lässt ein Hook nicht in `.claude/HANDOFF.md` des Haupt-Repos schreiben.
- Text nach aussen: keine Gedankenstriche, keine Doppelpunkte oder Semikolons im Fliesstext,
  Schweizer Schreibweise (Skill `my-seo-swiss-writer`).
