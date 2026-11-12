# Home Hub — Konfigurator

One-Page-Website mit interaktivem Produkt-Konfigurator für die Home-Hub-Familie — der lokale KI-Workspace für zu Hause (schreiben, planen, lernen) mit Home Kid-Modus für Kinder. Komplett ohne Cloud, ohne Mikrofon, ohne Kamera.

## Ansehen

Nach Aktivierung von GitHub Pages: `https://gipfellasse.github.io/Home-Hub-Konfigurator/`

## Features

- **5-Schritte-Konfigurator**: Modell → Speicher → Nutzerprofile → Zubehör → Zusammenfassung mit Vorbestell-Formular
- **3 Modelle**: Home Hub (1 Person, ab 349 €), Home Hub Pro (bis 4 Personen, ab 599 €), Home Hub Max (bis 10 Personen, ab 999 €) — je mit Home Kid-Ausbau
- **Home Kid**: kindersicherer Lernbereich (Hausaufgaben-Hilfe, Lernpläne, Offline-Wissensbibliothek, Eltern-Dashboard bei Max) — ohne Internet, ohne Werbung, ohne Fremdkontakte
- **KI-Workspace**: Texte schreiben & überarbeiten, zusammenfassen, übersetzen, Lernkarten, Pläne & Listen — alles lokal auf dem Gerät
- **Live-Preis**: Sticky Sidebar (Desktop) / Bottom-Bar (mobil), immer aktuell
- **Validierung**: Vorbestellung erst absendbar, wenn Modell & Speicher gewählt sind; Formular mit Fehlermeldungen pro Feld
- **Vergleichstabelle** zum Aufklappen, „So funktioniert’s“, Datenschutz-Sektion, FAQ-Akkordeon (10 Fragen)
- **Barrierefrei**: Skip-Link, Aria-Rollen für Radio-Gruppen, Labels überall, Fokus-Stile, `prefers-reduced-motion`-Support, 48px-Touch-Ziele
- **Mobile-first**, Design in Dunkelblau/Weiß mit dezenten Animationen

## Anpassen (nur Werte ändern)

Alle Produkte, Preise, Speicher, Zubehör, FAQ-Texte und Vertrauens-Punkte stehen als Datenobjekte ganz oben im `<script type="text/babel">`-Block der `index.html`:

- `PRODUCTS` — Modelle (Preis, Highlights, verfügbarer Speicher, kompatibles Zubehör, Home Kid-Ausbau)
- `STORAGES` — Speicheroptionen (Aufpreis, Erklärungstext)
- `ACCESSORIES` — Zubehör (Preis, Beschreibung, Max-Menge)
- `FAQ`, `HOW`, `PRIVACY_POINTS`, `COMPARE_ROWS` — Textinhalte
- `ORDER_ENDPOINT` — URL eines Formular-Endpunkts (z. B. Formspree). Ist er gesetzt, wird die Bestellung per `fetch` dorthin gesendet; sonst erscheint nur die Bestätigungs-Ansicht.

## Technik

- React 18 + ReactDOM + Babel Standalone per CDN (kein Build-Schritt nötig, GitHub Pages kompatibel; Internetverbindung beim Öffnen erforderlich)
- Eine einzige `index.html`, kein Backend
