# 🦋 FalterKataster – Funddatenbank & Fundort-Katalog

**FalterKataster** ist eine browserbasierte, vollkommen lokal funktionierende Webanwendung zur Erfassung, Verwaltung, Kartierung und wissenschaftlichen Auswertung von Insektenbeobachtungen (Schmetterlinge/Lepidoptera und andere Funddaten). 

Die Anwendung benötigt keine Server-Installation oder Datenbank-Backend: Alle Daten verbleiben datenschutzkonform direkt in Ihrem Browser (IndexedDB / LocalStorage) oder auf einem direkt angebundenen lokalen Ordner.

---

## 📑 Inhaltsverzeichnis
- [Highlights & Features](#-highlights--features)
- [Detailbeschreibung der Funktionen](#-detailbeschreibung-der-funktionen)
  - [1. Karte & Erfassung](#1-karte--erfassung)
  - [2. Kataloge (Arten & Fundorte)](#2-kataloge-arten--fundorte)
  - [3. Funde-Tabelle & Etikettendruck](#3-funde-tabelle--etikettendruck)
  - [4. Auswertung & Phänologie](#4-auswertung--phänologie)
  - [5. Export, Import & Datensicherheit](#5-export-import--datensicherheit)
- [Verwendete Technologien](#-verwendete-technologie)
- [Installation & Nutzung](#-installation--nutzung)
- [Lizenz](#-lizenz)

---

## 🌟 Highlights & Features

* 📍 **Punktgenaue Kartierung:** Interaktive Leaflet-Karte mit OpenStreetMap-Suche, automatischer Bestimmung von MTB (Meßtischblatt), Quadrant (Q) und Minutenfeld (MF) sowie Umrechnung von Dezimal- und DMS-Koordinaten.
* 📚 **Umfangreiche Kataloge:** Integrierter Artenstamm (inkl. K&R-Nummern, Roter Liste NDS/D und Direktlinks zum *Lepiforum*) sowie wiederverwendbarer Fundort-Katalog.
* 🏷️ **Professioneller Etikettendruck:** Druckvorstufe für Sammlungsetiketten im Millimeterbereich mit Anpassung von Abständen, Schriftgrößen, Rändern, Römischen Monatszahlen u.v.m.
* 📊 **Phänologische Auswertung:** Dynamische Diagramme zur Anzeige von Fundhäufigkeiten pro Kalenderwoche (über ein oder mehrere Jahre) inklusive kartografischer Visualisierung und PNG-Export.
* 💾 **100 % Lokal & Offline-fähig:** Funktioniert ohne externe Server-Datenbank. Unterstützung der **File System Access API** zur direkten Synchronisierung mit einem lokalen PC-Ordner.

---

## 🔍 Detailbeschreibung der Funktionen

### 1. Karte & Erfassung

Der Hauptbereich kombiniert eine interaktive Karte mit einem Eingabeformular zur schnellen Dokumentation von Sichtungen.

* **Kartennavigation & Geocoding:**
  * In der Karte klicken, um Koordinaten direkt zu übernehmen.
  * Integrierte **OpenStreetMap-Suche** nach Ortsteilen, Straßennamen oder Fluren.
  * Automatische Berechnung von:
    * **Dezimal-Koordinaten** (Lat / Lng)
    * **DMS-Format** (Grad, Minuten, Sekunden)
    * **MTB-Raster:** Meßtischblatt, Quadrant (1–4) und Minutenfeld (1–15).
* **Funddaten-Eingabe:**
  * **Datum & Uhrzeit:** Standardmäßig mit aktuellen Werten vorbelegt.
  * **Beobachter:** Speicherung des Bearbeiternamens.
  * **Art-Auswahl:** Intelligentes Autocomplete-Feld (Suche nach deutschem oder wissenschaftlichem Namen). Ein Klick zeigt Rote-Liste-Status und Direktlinks zum Lepiforum.
  * **Fundort-Vorlagen:** Auswahl bereits angelegter Fundorte überschreibt Koordinaten, Flur und MTB automatisch.
  * **Nachweis-Details:** Anzahl, Entwicklungsstadium (*Imago, Ei, Raupe/Larve, Puppe, Exuvie, Fraßspur*) und Methode (*Tagbeobachtung, Lichtfang, Köderfang, Kescher, Aufzucht*).
  * **Belegfotos:** Direktes Hochladen und Vorschau von Belegbildern.

---

### 2. Kataloge (Arten & Fundorte)

Verwaltung von Artenlisten und bekannten Fundorten inklusive Import- und Exportmöglichkeiten.

* **Arten-Katalog:**
  * Enthält vorinstallierte Stammdaten mit Systematik (Überfamilie, Familie, Gattung, Art, Autor), K&R-Nummer und Gefährdungsstufen (Rote Liste Niedersachsen / Deutschland).
  * Volltext-Filterung nach Namen oder taxonomischen Einheiten.
  * Einzelne Arten manuell anlegen oder bearbeiten.
  * Bulk-Import via **Excel (`.xlsx`)** oder **CSV**.
* **Fundort-Katalog:**
  * Wiederkehrende Exkursionsziele fest anlegen (Flur/Bezeichnung, Ort, PLZ, MTB/Q/MF, Seehöhe Min/Max, Habitatbeschreibung).
  * Verhindert Dubletten beim Import und füllt unvollständige Datensätze auf.

---

### 3. Funde-Tabelle & Etikettendruck

In der Funde-Tabelle werden alle erfassten Beobachtungen übersichtlich gelistet, gefiltert und für den Druck aufbereitet.

* **Tabellenansicht & Filter:**
  * Echtzeit-Filterung nach Art, Ort, Beobachter oder Freitext.
  * Bearbeitung und Löschung von Einzeleinträgen über Modals.
  * Belegfoto-Vorschau direkt in der Tabelle.
* **🏷️ Sammlungsetiketten-Generator (Druck-Engine):**
  * Erstellt druckfertige Etiketten für wissenschaftliche Sammlungen.
  * **Größenanpassung:** Exakte Maße in Millimetern (z. B. 40 × 20 mm, 30 × 15 mm) oder Voreinstellungen nutzen.
  * **Anzahl-Optionen:** Druck pro Fund oder automatisch Vervielfältigung je Individuen-Anzahl.
  * **Formatierung:** Datumsformate (ISO, TT.MM.JJJJ oder römische Monatszahlen `T.MM(röm.).JJJJ`), Dezimal- oder DMS-Koordinaten.
  * **Schnittlinien & Ränder:** Zuseitig konfigurierbarer Rand, Abstand und optionale Rahmen-Schnittlinien.
  * Live-Vorschau in Originalgröße.

---

### 4. Auswertung & Phänologie

Visualisierung von Nachweisen und phänologischen Abläufen.

* **Gefilterte Fundkarte:** Visualisiert alle Fundpunkte einer ausgewählten Art (oder aller Arten) innerhalb eines bestimmten Jahreszeitraums auf einer separaten Karte.
* **Phänologie-Diagramm (Kalenderwochen):**
  * Erstellt Balkendiagramme über das Auftreten pro Kalenderwoche (KW 1 bis KW 52).
  * Differenzierung nach **Nachweisen (Datensätzen)** oder **Individuensumme**.
  * Filterbar nach Entwicklungsstadium (*z. B. nur Imagines oder nur Raupen*).
* **Export:** Export des generierten Diagramms sowie der Auswertungskarte als **PNG-Grafik**.

---

### 5. Export, Import & Datensicherheit

Umfassende Schnittstellen zur Datensicherung und Weiterverarbeitung in GIS oder Tabellenkalkulationen.

* **Datenexporte:**
  * **CSV (Excel-kompatibel):** Semikolon-getrennt mit UTF-8 BOM.
  * **Excel (`.xlsx`):** Strukturierter Export aller Funde inklusive verknüpfter Art- und Fundortstammdaten.
  * **JSON:** Vollständiges Datenformat.
* **Datenimport:**
  * Einlesen von exportierten `.xlsx`-, `.csv`- oder `.json`-Dateien.
  * Intelligente Zusammenführung: Bekannte Datensätze werden aktualisiert, Dubletten übersprungen und neue Arten/Fundorte automatisch in die Kataloge übernommen.
* **Lokaler Ordner-Zugriff (File System Access API):**
  * Verbindung mit einem Ordner auf der Festplatte für direkte automatische Sicherungen.
  * Speichern der Datenbank lokal auf der Festplatte:  Export & Schnittstellen -> Datenordner verbinden -> Speicherort auswählen
* **Voll-Backup:** Sicherung der gesamten Datenbank inkl. eingebetteter Base64-Belegfotos in einer einzigen JSON-Datei.

---

## 🛠 Verwendete Technologie

Die Anwendung ist als reine **Single-Page-Application (SPA)** ohne externe Build-Tools umgesetzt:

* **HTML5 / CSS3:** Responsive Layout mit CSS-Variables und Flexbox/Grid.
* **JavaScript (ES6+):** Pure Vanilla JS für Logik und Datenbankspeicherung (IndexedDB).
* **Mapping:** [Leaflet.js](https://leafletjs.com/) (OpenStreetMap Tile-Layer).
* **Excel-Engine:** [SheetJS (xlsx)](https://sheetjs.com/) zum Parsen und Erstellen von `.xlsx`-Dateien.

---

## 🚀 Installation & Nutzung

1. Repository klonen oder ZIP-Archiv herunterladen.
2. Die Datei `fundkataster.html` einfach in einem modernen Webbrowser (Chrome, Firefox, Edge) öffnen.
3. Es ist **kein Webserver** und keine Installation erforderlich!

---

## 📄 Lizenz

Dieses Projekt ist unter der **MIT-Lizenz** veröffentlich – siehe die [LICENSE](LICENSE)-Datei für Details.
```

An updated `README.md` file describing all functions, features, and workflow specifications of the **FalterKataster** application has been created for your repository.
