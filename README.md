# PDFLito

PDFLito ist das PDF-Programm des Ingenieurbüros für Windows: PDF-Dateien ansehen, kommentieren,
stempeln, Seiten ordnen, Texte erkennen (OCR für Deutsch und Englisch, mit Umlauten und ß),
Pläne vermessen und Aufmaße erstellen.

In diesem Repository liegen nur die **fertigen Setup-Dateien** (unter
[Releases](../../releases)). Der Quelltext wird hier nicht veröffentlicht.

## Grundlage: PdfCraft (Open Source)

PDFLito ist eine Abwandlung des Open-Source-Programms
[**PdfCraft**](https://github.com/storytold/pdfcraft) (© ArtCraft Team und die
PdfCraft-Mitwirkenden). Geändert wurden unter anderem der Name, die Stempel, die Texterkennung
für Deutsch und die Voreinstellungen für Deutschland. PdfCraft und damit auch
PDFLito stehen unter zwei freien Lizenzen, zwischen denen man wählen kann:

- Apache License 2.0
- MIT License

Die Lizenztexte (`LICENSE-APACHE`, `LICENSE-MIT`) und die Datei `NOTICE.txt` mit den
vorgeschriebenen Hinweisen zu PdfCraft und den mitgelieferten Bestandteilen werden mit jedem Setup
in den Programmordner installiert. Für die Texterkennung enthält das Setup außerdem
Tesseract OCR und die Sprachdaten für Deutsch und Englisch (beide Apache License 2.0, die
Lizenztexte liegen im Programmordner unter `models\`).

Name, Schriftzug und Logos von ArtCraft sind Marken des ArtCraft Teams; sie sind nicht Teil der
freien Lizenzen (Einzelheiten in `NOTICE.txt`).

## Installation

1. Unter [Releases](../../releases/latest) die Datei **PDFLito-Setup-&lt;Version&gt;.exe**
   herunterladen.
2. Doppelklicken. Administratorrechte sind nicht nötig; PDFLito wird für den angemeldeten
   Benutzer installiert.
3. Auf Wunsch eine Desktop-Verknüpfung anlegen und PDFLito unter „Öffnen mit“ für PDF-Dateien
   anbieten lassen. PDFLito wird nie ungefragt zum Standardprogramm für PDF-Dateien.

Voraussetzung: Windows 10 oder 11, 64 Bit.

### Hinweis „Der Computer wurde durch Windows geschützt“

Das Setup ist nicht digital signiert. Windows (SmartScreen) zeigt deshalb beim ersten Start eine
Warnung. Dann auf **„Weitere Informationen“** und anschließend auf **„Trotzdem ausführen“**
klicken. Das ist bei selbst erstellten Programmen normal.

Wer sichergehen will, dass die Datei unverändert ist, vergleicht ihre Prüfsumme mit der Datei
`SHA256SUMS.txt` im selben Release (in PowerShell: `Get-FileHash PDFLito-Setup-<Version>.exe`).

## Updates

Am einfachsten über den **Lito Launcher**: Er zeigt die installierte und die neueste Version an
und installiert ein neues PDFLito automatisch, bevor das Programm das nächste Mal startet. Läuft
PDFLito gerade, wartet der Launcher mit dem Update, damit keine Arbeit verloren geht.

Ohne Launcher: das neue Setup herunterladen und einfach über die vorhandene Installation
installieren. Einstellungen und Dokumente bleiben erhalten.

PDFLito selbst sucht nicht nach Updates; das übernimmt allein der Launcher.

### Technische Hinweise (für den Launcher)

- Jedes Release enthält **zwei Dateien**: `PDFLito-Setup-<Version>.exe` und `SHA256SUMS.txt`.
  Ohne `SHA256SUMS.txt` installiert der Launcher das Update nicht.
- Der Launcher installiert still mit
  `/VERYSILENT /SUPPRESSMSGBOXES /NORESTART /SP- /NOCLOSEAPPLICATIONS /NORESTARTAPPLICATIONS /MERGETASKS=...`,
  bei einem Update zusätzlich `/DIR="<bisheriger Ordner>"`, bei einer Neuinstallation
  `/CURRENTUSER` (ohne Administratorrechte).

## Deinstallieren

Windows-Einstellungen > Apps > Installierte Apps > PDFLito > Deinstallieren.
