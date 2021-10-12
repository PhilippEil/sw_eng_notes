## PATH variable

## Navigation
cd, pwd, ls

how does `.` and `..` work?

# Manipulate files and folders
## :pencil2: touch - neue Datei erstellen oder Zeitstempel aktualisieren
touch kann zum Ändern der Zugriffs- und Änderungszeitstempel von Dateien verwendet werden. Aber auch das erstellen neuer, leerer Dateien ist möglich!

**Syntax**
```bash
touch [OPTION] file
```

**Wichtige Flags**
-a              Modifikation des Zugriffszeitstempels der Datei
-m              Modifikation des Änderungszeitsempels der Datei
-c --no-create (Wenn keine Datei vorhanden ist:) Keine Datei erstellen)

### Beispiel
***Leere Datei erzeugen***
Eine leere Datei wird erzeugt, wenn keine Datei mit dem gewählten Namen vorhanden ist und die -c bzw. --no-create Flag nicht gesetzt ist. 
```bash
touch sw_engineering.txt
```

***Zeitstempel einer exisiterenden Datei aktualisieren***
Mit dem befehl ```stat file``` werden unter Anderem die Zeitstempel einer Datei angezeigt.

```bash
stat sw_engineering.txt

Access: 2021-10-12 16:27:54.991475500 +0200
Modify: 2021-10-12 16:27:54.991475500 +0200
Change: 2021-10-12 16:27:54.991251300 +0200
Birth: 2021-10-12 16:27:54.986804300 +0200
```
Durch anwenden von ```touch``` auf eine bestehenden Datei werden die Zeitstempel "Acess, Modify und Change" auf die aktuelle Systemzeit gesetzt.

```bash
touch sw_engineering.txt

stat sw_engineering.txt
Access: 2021-10-12 16:31:50.631493000 +0200
Modify: 2021-10-12 16:31:50.631493000 +0200
Change: 2021-10-12 16:31:50.631223200 +0200
Birth: 2021-10-12 16:27:54.986804300 +0200
```

## :taxi: mv - move (rename) files
mv verschiebt Dateien und Verzeichnisse, dadurch können Dateien oder Verzeichnisse auch ganz einfach umbenannt werden. Es wird immer erst die Quelle und dann das Ziel angegeben.

**Syntax**
```bash
        mv [OPTION]... [-T] SOURCE DEST
  or:   mv [OPTION]... SOURCE... DIRECTORY
  or:   mv [OPTION]... -t DIRECTORY SOURCE...

```

**Wichtige Flags**
-v                                                               Steht für “verbose” und Zeigt alles an was der Befehl mv gerade macht
-i                                                               führt dazu, dass mv nach Benutzerrechten fragt, bevor eine bestehende Datei überschrieben wird
-n                                                              überschreibt keine bestehenden Dateien
-b                                                              erstellt eine Backup über die Zieldateien
        
### Beispiele:
**Verschiebt die Datei „test.txt“ von „/home/user/“ nach „tmp/“**
```bash
mv /home/user/test.txt /tmp/  
```
**Die Datei test.txt wird in test2.txt Umbenannt, dies funktioniert genau so auch mit Verzeichnissen**
```bash
mv test.txt test2.txt
```
**Verschiebt den Ordner „user“ aus dem Verzeichnis „home“ nach „/tmp/“**
```bash
mv /home/user /tmp/   
```
**Verschiebt alle Dateien die mit „.txt“ enden nach „/tmp/“**
```bash
mv *.txt /tmp/  
```                                        
### :file_folder: mkdir
Mit `mkdir` (*engl. make directory*) kann ein neues Verzeichnis erstellt werden.
Dem Befehl folgt eine Liste von Pfadnamen als Argument.

#### Beispiel ohne Parameter
```bash
mkdir [Verzeichnisname]
```
#### Parameter
`-p`: Wenn kein Verzeichnis existiert, wird ein neues erstellt. Bei vorhandenem Verzeichnis wird einfach fortgefahren.</p>
`-v`: Auf der Konsole können die erstellen Verzeichnisse ausgegeben werden.</p>
`-m`: Hinter dem Parameter kann als Oktalwert die Berechtigung für das Verzeichnis angegeben werden. 

#### Beispiel mit Parameter
```bash
mkdir -p /dokumente/neuerOrdner/test
```
## Output files
less, more, cat

## pipes
`|` and `>`
