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

**Wichtige Flags**\
-a              Modifikation des Zugriffszeitstempels der Datei\
-m              Modifikation des Änderungszeitsempels der Datei\
-c --no-create (Wenn keine Datei vorhanden ist:) Keine Datei erstellen)

### Beispiel
***Leere Datei erzeugen***\
Eine leere Datei wird erzeugt, wenn keine Datei mit dem gewählten Namen vorhanden ist und die -c bzw. --no-create Flag nicht gesetzt ist. 
```bash
touch sw_engineering.txt
```

***Zeitstempel einer exisiterenden Datei aktualisieren***\
Mit dem befehl ```stat file``` werden unter Anderem die Zeitstempel einer Datei angezeigt.\

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
-v                                                              Steht für “verbose” und Zeigt alles an was der Befehl mv gerade macht\
-i                                                              führt dazu, dass mv nach Benutzerrechten fragt, bevor eine bestehende Datei überschrieben wird\
-n                                                              überschreibt keine bestehenden Dateien\
-b                                                              erstellt eine Backup über die Zieldateien\
        
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

## :camera: cp - copy files and directories
cp kopiert Dateien und Verzeichnisse. Dabei wird immer erst die Quelle und dann das Ziel angegeben

**Syntax**
```bash
cp [optionen] quelle ziel

```

**Wichtige Flags**
-a                                                              Steht für „archive“. Mit diesem Schalter werden Zeitstempel, Besitzer, Gruppen, Dateirechte wie von der Quelle beibehalten\
-b                                                              erstellt eine Backup\
-r                                                              Steht für „rekursiv“. Mit diesem Schalter werden alle Ordner und Unterordner inkl. Dateien kopiert. Also ganze Verzeichnisbäume\
-v                                                              Steht für “verbose” und Zeigt alles an was der Befehl cp gerade macht\
        
### Beispiele:
**Kopiert die Datei „test.txt“ aus /home/user/ nach /tmp**
```bash
cp /home/user/test.txt /tmp/
```
**Kopiert alle Dateien und Unterordner von /home/user/ nach /tmp/**
```bash
cp -r /home/user/ /tmp/	
```
**Kopiert alle Dateien und Unterordner von /home/user/ nach /tmp/ und behält dabei alle Zeitstempel, Dateirechte, Benutzer und Gruppen des Originals (Der Quelle)**
```bash
cp -ar /home/user/ /tmp/	 
```

## :bomb: rm - remove file
rm löscht Dateien und Verzeichnisse

**Syntax**
```bash
rm [OPTION]... FILE
```

**Wichtige Flags**
-i                                                             Steht für interactive. Fragt bei jedem Löschvorgang ob die Datei wirklich gelöscht werden soll, dies muss dann mit der Taste „y“ bestätigt werden\
-f  --force                                                    Steht für "force". Bei der Ausführung des Befehls lösen nicht vorhandene Dateien und Ordner keine Fehlermeldung aus. Diese Flag eignet sich gut für Skripte.
-r                                                             Steht für „recursive“. Hier werden alle Dateien und Ordner rekursiv vom angegebenen Pfad gelöscht\
-v                                                             Steht für „verbose“ und Zeigt alles an was der Befehl rm gerade macht
        
### Beispiele:
**Löscht die Datei „meinedatei.txt“ im aktuellen Arbeitsverzeichnis**
```bash
rm meinedatei.txt	
```
**Löscht das Verzeichnis /tmp inkl. aller Dateien und Unterordner (rekursiv)**
```bash
rm -r /tmp	
```
**Löscht das Verzeichnis /tmp inkl. aller Dateien und Unterordner (rekursiv) und Zeigt dabei genau an was es gerade macht (verbose)**
```bash
rm -rv /tmp	
```
**Löscht das Verzeichnis /tmp inkl. aller Dateien und Unterordner (rekursiv) und fragt bei jedem Löschvorgang nach ob es dies auch wirklich machen soll**
```bash
rm -ri /tmp
``` 
                                  
## :file_folder: mkdir
Mit `mkdir` (*engl. make directory*) kann ein neues Verzeichnis erstellt werden.\
Dem Befehl folgt eine Liste von Pfadnamen als Argument.

**Syntax**
```bash
mkdir [Verzeichnisname]
```
**wichtige Flags**
`-p`: Wenn kein Verzeichnis existiert, wird ein neues erstellt. Bei vorhandenem Verzeichnis wird einfach fortgefahren.</p>
`-v`: Auf der Konsole können die erstellen Verzeichnisse ausgegeben werden.</p>
`-m`: Hinter dem Parameter kann als Oktalwert die Berechtigung für das Verzeichnis angegeben werden. 

### Beispiel mit Parameter
```bash
mkdir -p /dokumente/neuerOrdner/test
```
## Output files
less, more, cat

## pipes
`|` and `>`
