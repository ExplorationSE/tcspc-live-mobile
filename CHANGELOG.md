# Änderungsprotokoll – TCSPC Live Mobile

> Bis Version 1.0.8 hieß das Projekt „ExplorationSE Harp Mobil“ (Repository `ExplorationSE/harp-mobil`), bis 1.0.7
> „ExSE Harp Mobil“ (Repository `ExplorationSE/exse-harp-mobil`, davor „ExSE Harp Mobile“). Die älteren Einträge
> behalten den damaligen Namen.

## 1.1.0 – 20.11.2026

Umbenennung, keine Funktionsänderung.
- Neuer Name **TCSPC Live Mobile** mit dem Untertitel „Live-Histogramme und g² – für PicoQuant HydraHarp 500“:
  Kopfzeile und Infobereich der App, Seitentitel, App-Manifest, Anmeldeseite, `/api/health`, Server- und
  Skriptmeldungen, README, Anleitung und PDF.
- Unabhängigkeits- und Markenhinweis oben im README, auf der Titelseite der Anleitung und im Infobereich der App.
- GitHub-Repository umbenannt in `ExplorationSE/tcspc-live-mobile` (alte Adressen leiten weiter);
  Download-Dateien heißen jetzt `tcspc-live-mobile-…zip`. Ordner im Zip (`v1`), Installationsordner
  `C:\HarpMobil\v1`, Python-Paket `harp` und Umgebungsvariablen `HARP_*` bleiben unverändert; bestehende
  Installationen funktionieren an ihrem Ort weiter.
- Service-Worker-Cache `harp-mobil-1.1.0-r1`; Einstellungen im Browser bleiben erhalten. Wer die App auf dem
  Startbildschirm hat, kann sie entfernen und neu hinzufügen, damit der neue Name erscheint.
- Demodateien unverändert.

## 1.0.8 – 19.10.2026

Umbenennung, keine Funktionsänderung.
- Neuer Name **ExplorationSE Harp Mobil** (vorher „ExSE Harp Mobil“): Seitentitel, App-Name im Manifest,
  Infobereich, Anmeldeseite, `/api/health`, Server- und Skriptmeldungen, README und Anleitung (PDF neu erzeugt).
  Oben in der App steht weiterhin kurz „Harp Mobil“ (Kurzname im Manifest unverändert).
- GitHub-Repository umbenannt in `ExplorationSE/harp-mobil` (alte Adressen leiten weiter);
  Download-Dateien heißen jetzt `harp-mobil-…zip`. Der Ordner im Zip heißt weiterhin `v1`.
- Service-Worker-Cache `harp-mobil-1.0.8-r19` (alte Caches werden beim Aktivieren gelöscht). Die gespeicherten
  Einstellungen im Browser (`harp.*`) bleiben erhalten. Wer die App auf dem Startbildschirm hat, kann sie entfernen
  und neu hinzufügen, damit der neue Name erscheint.
- Anleitung-PDF neu erzeugt, jetzt mit `tools/make_anleitung_pdf.py` (wie in GX); Screenshot des Infobereichs
  im README aktualisiert. Kasten „… ist ONLINE“ im Startfenster etwas breiter, damit der längere Name passt.
- Installationsordner in Anleitung und README: `C:\HarpMobil\v1` (bisher `C:\HarpMobile\v1`); bestehende
  Installationen funktionieren an ihrem Ort unverändert weiter.
- Demodateien unverändert.

## 1.0.7 – 17.10.2026

- App: Im T2-Modus gibt es keine Kachel „Sync“ mehr (bisher stand bei T2-Dateien ohne K0-Ereignisse eine
  Kachel „Sync 0“). Der Sync-Eingang ist bei T2 ein normaler Datenkanal und erscheint als eigene Kachel „K0“
  nur, wenn die Datei K0-Ereignisse enthält.
- App: Infobereich bei T2 ohne Sync-Rate („T2, 4 Kanäle“ bzw. „T2, 4 Kanäle + K0“). T3 unverändert
  (Kachel „Sync“, „Sync … cps“ im Infobereich).

## 1.0.6 – 13.10.2026

Stabiler Betrieb mit mehreren Handys gleichzeitig.
- Server: Jede Verbindung hat eine eigene Sende-Warteschlange (Frame und Status nur jeweils der neueste,
  Quittungen in Reihenfolge). Ein hängendes Handy (Bildschirm aus, Hintergrund, Funkloch) blockiert weder
  andere Handys noch die Befehlsverarbeitung.
- Server: Hängt das Senden an ein Handy länger als 5 s, wird dessen Verbindung aktiv geschlossen (vorher blieb
  sie als „Zombie“ offen: eingefrorene Anzeige ohne Wiederverbindung); eine gehaltene Steuerung wird freigegeben.
- App: Verbindungsprüfung per Ping alle 5 s; kommt 10 s lang keine Antwort, wird neu verbunden. Beim
  Zurückkehren in den Vordergrund wird die Verbindung sofort geprüft. Hinweis „Verbindung wird wiederhergestellt …“.
- App: Zuschauer-Modus deutlich gekennzeichnet („Nur Anzeige“); Hinweis nach Wiederverbindung, wenn die
  Steuerung bei der Unterbrechung verloren ging.
- Tests mit zwei gleichzeitigen Clients, einer davon hängend.

## 1.0.5 – 13.10.2026

- `install_windows.bat`: Python-Suche robuster (py -3.13, -3.12, -3.11, -3, py, python; jeder Kandidat wird
  ausgeführt und geprüft, mind. 3.10, 64 Bit). Behebt Fehlstart mit dem neuen Python-Installationsmanager
  („No runtime installed that matches 3.13“). Klare Meldung mit Hinweis `py install 3.13`; Abbruch vor
  venv/pip, wenn kein Python gefunden wird oder die venv nicht angelegt werden kann.

## 1.0.4 – 13.10.2026

Textänderung, keine Funktionsänderung.
- Infobereich-Hinweis in der App gekürzt: „Simulation mit synthetischen PTU-Dateien – diese Version enthält noch keine
  Schnittstelle zu einer echten HydraHarp.“ (Herkunftshinweis bleibt im README).
- Service-Worker-Cache neu (`exse-harp-mobil-1.0.4-r15`).

## 1.0.3 – 13.10.2026

Umbenennung, keine Funktionsänderung.
- Neuer Name **ExSE Harp Mobil** (vorher „ExSE Harp Mobile“): Seitentitel, App-Name (Kurzname „Harp Mobil“),
  Infobereich, Anmeldeseite, `/api/health`, Skripte, README, Anleitung und PDF.
- GitHub-Repository umbenannt in `ExplorationSE/exse-harp-mobil` (alte Adresse leitet weiter);
  Download-Dateien heißen jetzt `exse-harp-mobil-…zip`.
- Service-Worker-Cache neu (`exse-harp-mobil-1.0.3-…`); ggf. die alte installierte App vom Startbildschirm entfernen
  und neu hinzufügen, damit der neue Name erscheint.

## 1.0.2 – 13.10.2026

Hinweise zu Status und Herkunft, keine Funktionsänderung.
- README: Hinweiskasten oben – noch keine Anbindung an eine echte HydraHarp (nur Simulation aus PTU-Dateien,
  snAPI-Quelle unter Windows ungetestet, Gerätequelle Platzhalter); erstellt ausschließlich aus öffentlich
  verfügbaren Informationen, keine PicoQuant-Dateien enthalten; kein Produkt der PicoQuant GmbH, Marken,
  keine Gewährleistung, nicht für sicherheitskritische Anwendungen.
- App: kurzer Hinweis und Kennzeichen „Simulation“ im Infobereich; Manifest-Beschreibung angepasst.
- Repository-Beschreibung: „Simulation, noch ohne Geräteanbindung“.
- Demodateien umbenannt, damit sie klar als synthetisch erkennbar sind (Inhalt unverändert):
  `Demo_Synthetisch_T3_Fluoreszenz_4Kanal_5min.ptu`, `Demo_Synthetisch_T2_Einzelphotonen_HBT_90s.ptu`,
  `Demo_Synthetisch_T2_Heralded_K0_HBT_60s.ptu`; Standarddatei in `config.toml` angepasst.
  Die alten Dateien `data\Demo_T3_…`, `data\Demo_T2_…` können gelöscht werden.

## 1.0.1 – 13.10.2026

Nur Dokumentation und Projektpflege, keine Funktionsänderung.
- MIT-Lizenz (`LICENSE`); Hinweis auf uPlot (MIT) bleibt in `web/vendor/LICENSE-uPlot.txt`.
- GitHub Actions: pytest bei jedem Push (Python 3.11 und 3.13), Test-Badge im README.
- README: neuer Kopf mit Zweck, Download-Link zur aktuellen Version, Abschnitt „Funktionen“,
  Screenshots, Kapitel „Lizenz“; Kapitelreihenfolge 4/4a korrigiert; „V1“ → „1.0“.
- Version 1.0.1, Service-Worker-Cache erneuert.

## 1.0.0 – 13.10.2026

Erste Version. Live-Anzeige von Messdaten einer PicoQuant HydraHarp 500 im Browser/Handy,
in dieser Version als Simulation durch Wiedergabe von PTU-Dateien.

### Server
- FastAPI + WebSocket, Frames mit Histogramm, Korrelation und Zählraten (wenige kB pro Bild).
- PTU-Leser für T2 und T3 (u. a. Generic T2/T3, HydraHarp V1/V2), Gegenprobe mit `ptufile`.
- Wiedergabe in Echtzeit oder schneller/langsamer, Akkumulieren oder gleitendes Fenster, Datei wiederholen.
- Steuerung durch genau einen Client (Übernahme/Freigabe), Zuschauer sehen live mit.
- Zugangscode mit Cookie, Origin-Prüfung, Befehlsprotokoll.
- Einzige Versionsquelle `harp/__init__.py`, abrufbar über `/api/health`.

### Messansichten
- **Histogramm** (log): T3 Mikrozeit nach Sync; T2 Zeit seit dem letzten Ereignis auf dem Referenzkanal.
- **Korrelation (g²)** (log): τ = t(Kn) − t(Kref) für T2 und T3 (T3 mit absoluter Zeit), alle Paare im
  symmetrischen Fenster, auch über Frame-Grenzen hinweg; Referenzkanal und Binbreite wählbar.
- **Zeitverlauf**: Zählraten (kcps) über der Dateizeit.
- T2: Sync-Eingang als eigener Datenkanal **K0** (wenn die Datei Sync-Ereignisse enthält).
- Startwerte für Binbreite/Fenster je nach Datei (Sync-Periode bzw. Herald-Koinzidenzen im ns-Bereich).

### Oberfläche (PWA)
- Handy-optimiert: einzeilige Kopfzeile mit Ansichtsumschalter „Histo | g² | Zeit“ und Kanaltasten K0–K4.
- Diagramme symmetrisch in der Karte zentriert; Zählratenkacheln in einer Zeile.
- Fortschrittsbalken direkt unter den Start-Tasten; Versionsanzeige im Infobereich.
- Jede PTU-Datei erscheint genau einmal in der Auswahl (Windows: keine Doppelten mehr).

### Windows-Betrieb
- `install_windows.bat`, `start_server.bat` (lokales Netz), `start_online.bat`/`stop_online.bat`
  (Internetzugriff über Cloudflare Quick Tunnel, mit QR-Code und Zugangscode), Anleitung als PDF.

### Demodaten
- `Demo_T3_Fluoreszenz_4Kanal_5min.ptu`: 4 Kanäle, Fluoreszenzabklingen, 5 min.
- `Demo_T2_Einzelphotonen_HBT_90s.ptu`: Einzelphotonenquelle, HBT, Antibunching.
- `Demo_T2_Heralded_K0_HBT_60s.ptu`: Herald-Einzelphotonen, K0 = Herald, Koinzidenzen bei +12/+15 ns.
