# CLAUDE.md - diktiv-website

## Diktiv Projekt-Struktur (WICHTIG!)

**Diktiv besteht aus drei separaten Repositories/Verzeichnissen:**

| Verzeichnis | Zweck | GitHub Repo | Zugriff |
|-------------|-------|-------------|---------|
| **X:\Wisper** | Source Code, Development | github.com/aebionix/Wisper | Privat |
| **X:\diktiv-releases** | Releases, update-info.json | github.com/aebionix/diktiv-releases | Öffentlich |
| **X:\diktiv-website** | Website (index.html) | github.com/aebionix/diktiv-website | Öffentlich |

## Dieses Repo (diktiv-website)

**Zweck:** Öffentliche Website für Diktiv (diktiv.ch)

**Inhalt:**
- `index.html` - Hauptseite (Single-Page)
- `favicon.svg` - Logo

**Premium-Features aktualisieren:**

Wenn neue Premium-Features hinzugefügt werden, die Premium Edition Liste in `index.html` aktualisieren:

```html
<!-- Zeile ~1168: Premium Edition Features -->
<li>
    <svg class="check" ...></svg>
    <strong>Feature-Name</strong>
</li>
```

**Deployment:**

Website wird via GitHub Pages gehostet:
- Push zu `main` Branch → Automatisches Deployment
- URL: https://diktiv.ch (oder GitHub Pages URL)

## Andere Repos

- **Source Code:** `X:\Wisper`
- **Releases:** `X:\diktiv-releases`
