# Find - Dateisuche unter Linux
Dient der Dateisuche in Verzeichniszweigen. Hier kann ein Startpunkt definiert werden, welcher auf vielfältige Weise filter anwenden kann.<br>
Zum Beispiel, Dateinamen, -alter, -groesse, -berechtigung.<br>

An den unten aufgeführten Beispielen, zeige ich euch, wie solche Vielfältigen Möglichkeiten den Alltag unter Linux vereinfachen kann.<br>

![TIP]<br>
Sollten unter euch Bash-Skript Entwickler sein, nutzt in euren Bash-Skripten 'find' statt 'ls' fuer Rekursive Auflistungen :)
### Beispiel
```bash
$ find /usr/share/ -name '*.jpg'
1.jpg 2.jpg 3.jpg
```

```bash
$ find /lib64/ -size +10M
große-datei.txt
```

```bash
$ find /dev/ -nmin -1
dasIstEinText.txt
```

```bash
$ find -name 'a*'
andrew_day.jpg and_birthday.jpg aal_glatt.jpg
```

## Groß- kleinschreibung sind hier irrelavant mit dem Parameter -iname
```bash
$ find -iname 'a*'
andrew_day.jpg Adidas.jpg aAl_glatt.jpg
```

## Suche nach modifizierten Dateien (Minute, Tage, letztes mal gelesen)

Modifikation = Erstellen oder Editieren<br>
Modifizierte Zeit != Zeitwechsel<br>
-> Modifizierter Inhalt, Aenderungen von Metadaten

```bash
find -mmin [minute]
find -mmin -5
find -mmin +5
modifizierte Minuten
```

```bash
find -mtime 2
#24-hour periods
```

```bash
find -cime -5
#Change Minute
```

## Suche nach Dateien Größe

```bash
find -size [groesse]
find -size 512k
find -size +512k -> Groesser als 512 kb
find -size -512k -> kleiner als 512 kb
```

## Suche mit Operatoren AND,OR,NOT
```bash
find -name "f*" -size 512k -> AND
find -not -name "f*" -> NOT
find -or -name "a*" -> OR
```

## Suche nach Berechtigungen

```bash
find -perm 664 -> Finde Dateien mit exakt diesen Berechtigungen
find -perm -664
find -perm /664 -> Finde Dateien mit diesen Berechtigungen
find -perm -100
```
[!TIP]
## Sowas könnte in einer LFCS Prüfung vorkommen 
### Finde Dateien mit den Berechtigungen 666 unter foldendem Pfad
### und loesche alle Dateien die die Attribute beinhalten.
```bash
find /opt/ -perm -666 -type f -exec rm -f {} \;
```

### Finde unter folgendem Ordner, Dateien die das SETUID gesetzt haben.

```bash
find /opt/ -perm /4000
```

### Finde Datien die exakt 1 byte Groß sind unter /path/ und verschiebe diese Datei/en in den Ordner /path/folder
```bash
sudo find /path/ -type f -size 1c -exec mv {} /path/folder/ \;
```

### 


# Was haben wir davon?