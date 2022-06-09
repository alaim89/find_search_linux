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


# Search


```bash
$ find -name 'a*'
andrew_day.jpg and_birthday.jpg aal_glatt.jpg
```

## Groß- kleinschreibung sind hier irrelavant mit dem Parameter -iname
```bash
$ find -iname 'a*'
andrew_day.jpg Adidas.jpg aAl_glatt.jpg
```


# Was haben wir davon?