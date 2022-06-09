# Find

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

Modifikation = Erstellen oder Editieren
Modifizierte Zeit != Zeitwechsel
-> Modifizierter Inhalt, Aenderungen von Metadaten

```
find --mmin [minute]
find --mmin -5
find --mmin +5
modifizierte Minuten
```

```
find -mtime 2
#24-hour periods
```

```
find -cime -5
#Change Minute
```

## Suche nach File Größe

```
find -size [groesse]
find -size 512k
find -size +512k -> Groesser als 512 kb
find -size -512k -> kleiner als 512 kb
```

## Suche mit Operatoren AND,OR, NOT
```
find -name "f*" -size 512k -> AND
find -not -name "f*" -> NOT
```

## Suche nach Berechtigungen
```
find -perm 664 -> Finde Dateien mit exakt diesen Berechtigungen
find -perm -664
find -perm /664 -> Finde Dateien mit diesen Berechtigungen
find -perm -100
```




# Was haben wir davon?