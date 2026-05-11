## setup:
1. Lego Studio runterladen
 https://www.bricklink.com/v3/studio/download.page "Changelog and older versions" ausklappen für Windows Versionen!!
2. Github Account erstellen 
3. Mir den Nutzernamen mitteilen damit ich dich zum Repo hinzufügen kann
4. Git Bash downloaden https://git-scm.com/install/windows 
5. Github und lokalen PC verbinden: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh
 (kompletten guide durcharbeiten)
6. Mit Datei Explorer oder Git Bash zum Verzeichnis navigieren in welches die Dateien hinkommen sollen
    - probiere rechte Maustaste im geöffneten Verzeichnis "öffnen mit git bash"
    - nutze cd - Befehl: cd pfad
  z.b. "cd Downloads"
7. In Git Bash folgende Befehle eingeben:
```
git config --global user.name nutzername
git config --global user.email nutzer@domain.com
git config --global pull.rebase true
git clone git@github.com:wiredkonst/cubeChecker.git
```
8. Lego Studio starten
9. Über Button "open a file" die Datei cubeChecker.io öffnen
10. Die Teileliste importieren:
    1. Oben links auf "Main" draufdrücken damit sich ein Dropdown öffnet
    2. im Dropdown auf "config" drücken
    3. im geöffneten Fenster auf "choose a way..." drücken
    4. im Dropdown auf "import a wanted list xml w/ quantity" drücken
    5. im geöffneten Fenster pieces.xml wählen, bestätigen und geöffnete Fenster schließen
11. Die Teileliste (Palette) selektieren:
    1. Oben links auf "Main" draufdrücken damit sich ein Dropdown öffnet
    2. im Dropdown "pieces" drücken
12. unten links sind nun alle verfügbaren Teile aus den Sets: 2x Ev3 Mindstorms + 1x Ev3 Expansion Set aufgelistet. Usage hints:
 - Steine platzieren per dragndrop
 - by default kann man nur dort platzieren wos "hinpasst", das kann aber getoggelt werden: oben links auf "Snap" drücken 
 - Selektierte Teile rotieren: Taste R drücken
 - Selektierte Teile kopieren: Taste C drücken
 - Selektierte Teile bewegen: Taste M drücken


## optional: einen Würfel importieren
1. Part Designer runterladen https://www.bricklink.com/v3/studio/partdesigner.page "Changelog and older Versions" ausklappen für Windows Versionen
2. Setup ausführen, wird nach Verzeichnis für Lego Studio fragen, iwas mit "C:\Program Files\Studio 2.0" musses sein
3. Part Designer starten
4. "import" drücken und im Tab 3D Object cube.obj selektieren
5. scale auf 3900 % setzen; insert drücken
6. 3D Würfel selektieren und oben rechts "export to studio" drücken + Folgedialog bestätigen
7. Lego Studio starten
8. Soeben importer Würfel befindet sich nun in der Palette "custom parts"
9. Benutzte Würfel bevor Änderungen commitet werden wieder entfernen


## Das hier tun jedes mal wenn am Modell weitergearbeitet werden möchte:
1. Git Bash öffnen im Verzeichnis mit der .io Datei
2. folgende Befehle ausführen:
```
ssh -T git@github.com
git pull origin master
```
3. .io Datei in Lego Studio öffnen (wird nicht automatisch refreshed) 
4. Modell bearbeiten
5. Wenn fertig: Datei speichern
6. In Git Bash folgende Befehle ausführen:
```
 git add cubeChecker.io
 git commit -m "Änderungen hierhin schreiben"
 git pull origin master
```
 -> wenns beim letzten zu "merge conflict" kommt, mir die .io Datei schicken und Befehl "git rebase --abort" ausführen
```
git push origin master
``` 