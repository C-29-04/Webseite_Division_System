# Division System Website - Setup Instructions

## Hintergrundbild einrichten

Bitte kopieren Sie das Bild `Calvin-Speaker-Stich1.jpg` von:
```
/Users/pforsten/Downloads/CalvinWebSite/Calvin-Speaker-Stich1.jpg
```

Nach:
```
/Users/pforsten/Development/svelte/Webseite_Division_System/static/Calvin-Speaker-Stich1.jpg
```

## Installation und Start

1. Installieren Sie die Dependencies (falls noch nicht geschehen):
```bash
npm install
```

2. Starten Sie den Entwicklungsserver:
```bash
npm run dev
```

3. Öffnen Sie http://localhost:5173 in Ihrem Browser

## Features

- **Responsives Design**: Die Website passt sich automatisch an verschiedene Bildschirmgrößen an
- **Burger Menu**: Auf mobilen Geräten wird die Navigation als Hamburger-Menü dargestellt
- **Parallax-Effekt**: Das Hero-Bild bewegt sich beim Scrollen
- **Kontaktformular**: Vollständiges Formular mit Validierung
- **Tailwind CSS**: Verwendet RAL 7016 Grautöne und ein minimalistisches Design

## Anpassungen

- Die Farben können in `tailwind.config.js` angepasst werden
- Das Logo und die Navigation können in `src/lib/components/Header.svelte` geändert werden
- Der Footer-Inhalt kann in `src/lib/components/Footer.svelte` angepasst werden
