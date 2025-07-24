Tcl/Tk Grid Layout Demo
========================

Dies ist eine lehrreiche Tcl/Tk-Anwendung zur Veranschaulichung des `grid`-Geometriemanagers mit Fokus auf:

- Spalten- und Zeilenkonfiguration
- Verwendung von `-weight` und `-uniform` zur flexiblen Größenverteilung
- Einsatz von `ttk::frame`, `ttk::label`, `ttk::entry`
- Dynamische Größenanpassung beim Fenster-Resize

Projektziel
-----------

Demonstration eines modernen, anpassbaren Formular-Layouts mit `ttk::frame` und `grid`, geeignet für grafische Eingabemasken, Formulare oder Dialogfenster.

Dateistruktur
-------------

- `main.tcl`        - Hauptprogramm mit Grid-Layout
- `README.md`       - Diese Dokumentation
- `img/`            - Optionales Verzeichnis für Screenshots oder Beispielbilder
- `style.tcl`       - (Optional) Style-Definitionen ausgelagert

Ausfuehrung
-----------

Voraussetzung: Tcl/Tk Version 8.6 oder hoeher

Aufruf unter Linux/macOS:

    tclsh main.tcl

Unter Windows:

    doppelklick auf main.tcl
    oder
    tclsh.exe main.tcl

Funktionen
----------

- GUI mit Labels, Eingabefeldern und Bildanzeige
- Gleich breite Spalten durch `-uniform`
- Flexible Groessenanpassung durch `-weight`
- Hintergrundfarben via `ttk::style`
- Feste Rahmenabmessung durch `pack propagate off`

Quellcodeauszug
---------------

Beispielkonfiguration von Spalten und Widgets:

    grid .main.l1 -row 0 -column 0 -sticky e
    grid .main.e1 -row 0 -column 1 -sticky we

    grid columnconfigure .main 0 -weight 1 -uniform col
    grid columnconfigure .main 1 -weight 1 -uniform col

    # Beide Spalten dehnen sich gleichmaessig aus

Sticky-Werte:

- n: oben
- s: unten
- e: rechts
- w: links
- Kombinationen wie `nsew` bedeuten volle Dehnung

Kurzanleitung Grid
------------------

Haeufig genutzte Optionen beim Platzieren mit `grid`:

| Option          | Beschreibung                                     |
|-----------------|--------------------------------------------------|
| -row            | Zeilennummer (beginnend bei 0)                   |
| -column         | Spaltennummer (beginnend bei 0)                  |
| -sticky         | Ausrichtung innerhalb der Zelle                  |
| -padx, -pady    | Aussenabstand horizontal bzw. vertikal           |
| -ipadx, -ipady  | Innenabstand innerhalb des Widgets               |
| -columnspan     | Widget belegt mehrere Spalten                    |
| -rowspan        | Widget belegt mehrere Zeilen                     |
| -weight         | Bestimmt, ob die Spalte/Zeile mitwaechst         |
| -uniform        | Gruppiert Spalten/Zeilen fuer gleiche Breite     |

Beispielausgabe
---------------

GUI mit:

- Labels: z.B. "Name", "Ort"
- Eingabefeldern (`entry`)
- Bildbereich mit `photo image`
- Gleichmaessiger Layout-Aufteilung

Tipps
-----

- Nicht `pack` und `grid` im selben Container mischen
- `grid propagate $container off` unterdrueckt automatische Groessenvorgabe
- `grid info $widget` zeigt aktuelle Grid-Zuordnung
- `grid columnconfigure . all -weight 1` dehnt alle Spalten gleichmaessig

Kompatibilitaet
---------------

- Tcl/Tk Version 8.6.0 oder hoeher
- Keine externen Abhaengigkeiten notwendig
- Optional: Screenshot im Ordner `img/` ablegen

Lizenz
------

MIT License

Mitwirken
---------

Pull Requests willkommen! Verbesserungsvorschlaege, neue Grid-Beispiele oder Style-Erweiterungen koennen gerne eingereicht werden.

Weiterfuehrende Links
---------------------

- Tcl/Tk Manual zu `grid`: https://www.tcl.tk/man/tcl8.6/TkCmd/grid.htm
- TkDocs Einfuehrung: https://tkdocs.com/
- ttk::style Dokumentation: https://www.tcl.tk/man/tcl8.6/TkCmd/ttk_style.htm

Erstellt fuer Lehrzwecke zur praktischen Anwendung von Tcl/Tk GUI-Techniken.
