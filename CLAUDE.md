# CLAUDE.md - diktiv-website

Öffentliche Website der Windows-Diktier-App Diktiv: **https://diktiv.com**.

**Zuerst lesen:** `docs/ai-handover.md` (Stand, Entscheide, Veröffentlichen, Fallstricke).

## Kurz

- Die Website ist der Ordner `site/`: statisches HTML, kein Build, kein Framework.
- Hosting bei Hostpoint (Schweiz), Upload über den Hostpoint-Dateimanager nach `www/diktiv.com`
  (Skill `my-hostpoint`). Ein Push auf `main` veröffentlicht nichts.
- Veröffentlichen nur nach Michaels «veröffentlichen». Danach jede hochgeladene Datei mit `curl`
  gegen die lokale Fassung vergleichen.
- Beschrieben wird nur die **Gratis-Version**. Jede Aussage am Code der App prüfen.
- Jede Seite gibt es auf Deutsch und Englisch. Änderungen immer an beiden Fassungen.

## Andere Repos

| Repo | Zweck | Ort |
|---|---|---|
| diktiv-next | Quellcode der App | `C:/Users/mike/source/repos/diktiv-next` (Forgejo `xonex/Diktiv`) |
| diktiv-website | diese Website | GitHub `aebionix/diktiv-website` |
