# Input und Output

Ein Algorithmus ist eine Rechenvorschrift, die eine Eingabe in eine Ausgabe umwandeln kann.

## Zeichenketten ausgeben

Strings (str) können in python zwischen `""` oder `''` definiert werden.
Die Funktion `print()` kann einen String als Parameter entgegennehmen und ihn ausgeben.
Sie kann aber auch beliebig viele Werte durch Komma getrennt entgegennehmen.
Diese werden mit einem Leerzeichen getrennt ausgegeben.
Sie fügt dem Ausgabewert am Ende eine neue Zeile hinzu.
Mit `end` kann der Abschluss (das Endzeichen) definiert werden.

```python
print("hello world", end="")
```

Auf die selbe Weise kann mit `sep` der Separator mehrer Werte definiert werden.

```python
print("Hello", "World", sep=",")
```

Zeichenketten können beliebig lang sein.
Um sie im Code auf mehrere Zeilen aufzuteilen, kann ich den Konkatenationsoperator `+` verwenden.

```python
print("Hello World. This text continues" +
	"on a new line")
```

Um einen Multiline comment zu definieren, wird der String zwischen dreifache `"""` gepackt.

```python
"""This is a mulitline comment.
It spans two lines"""
```

Strings können multipliziert werden.
Das heisst, sie können mehrfach aneinander gereit werden.

```python
print("Hello " * 3)
```

Python erlaub es nicht, Strings und Zahlen direkt zu verbinden.
Zahlen müssen zu Strings gecastet werden.

Spezialzeichen können in Strings mit dem `\` gekennzeichnet werden. 

## Methoden auf Zeichenketten verwenden

Die Klasse String bietet einige Methoden.

```python
name="chrigi"

# upper/lowercase
name.upper()
name.lower()

# findet position eines substrings
name.find("ig")

# boolean beginnt/endet mit string
name.startswith("ch")
name.endswith("gi")

# substring durch anderen string ersetzen
name.replace("gi","stian")

# Zeichen entfernen
name.strip("g")
```

Zeichenketten sind indexierbar:

```python
# Zeichen an position 2
name[2]

# erstes/zweites Zeichen von hinten
name[-1]
name[-2]

# slicing: Buchstabe 0 bis 2
name[0:2]

# Anfang bis 2 buchstabe / 2ter bis Schluss / zweitletzter bis schluss
name[:2]
name[2:]
name[-2:]
```

Um Nummern und Strings zu konkatenieren, muss die Zahl zu einem String gecasted werden.
Dazu wird die die `str()` Funktion verwendet.

```python
print("Ich bin " + str(25) + " Jahre alt")
```

## Formatierung

Um Zahlen für die Ausgabe zu formatieren kann die Funktion `format()` verwendet werden.

```python
number = 12345.6789

# eine Nachkommastelle
format(number, ".1f")A
# zwei Kommastellen und tausender trennzeichen
format(number, ",.2f")
# exponentialschreibweise
format(number, "e")

number = 12345
# tausendertrennzeichen ganze zahl
format(number, ",d")
# ganze Zahl, drei stellen (Nullen vorne)
format(number, "03d")

percentage = 0.883
# prozentschreibweise
format(percentage, "%")
#zwei nachkommastellen
format(percentage, ".2%")
```

### Ersatzfelder

Ein String kann Ersatzfelder vom format `{i}` enthalten.
Die `.format()` Methode kan diese Felder durch andere Inhalte ersetzen.

```python
age = 41
height = 1.76
message = "Ich bin {0} Jahre alt und {1} m gross."
print(message.format(age, height))
```

## Eingaben entgegennehmen

Die `input()` funktion wartet auf eine Eingabe des Nutzers.



