# Funktionen Planen und Programmieren

Oft werden Funktionen aus einer anderen Funktion aufgerufen.
Eine Funktion kann also die Aufrufende oder die Aufgerufene Funktion sein.

Wenn ein Programm komplexer wird macht es Sinn, es auf mehrere Dateien aufzuteilen.
Ein Modul kann ein anderes Modul mit `import` importiert werden.

Wenn ich also die Datei `movie_quote.py` importieren möchte, lautet der Befehl:

```python
import movie_quote
```

## Die Variable `__name__`

Immer wenn der Python Interpreter ein Datei liest stezt er ein paar spezielle Variablen und führt den gesammten Code aus.

Wenn ich also ein Modul importiere, dass Code hat, der nicht in einer Funktion ausgekapselt ist, wird dieser beim Import ausgeführt.

Wenn ein Modul der Einstiegspunkt eines Programms enthät wird die Vaiable `__name__ == "__main__"` definiert.

## Parameter an Funktionen übergeben

Der tatsächliche Paramter einer Funktion ist der Wert der effektiv an die Funktion übergeben wird.
Der formale Parameter ist der Platzhalter-Name die dem Wert in der Funktionsdefinition gegeben wird.

```python
def print_student(name, major, semester):
	print(name, "studiert", major, "im {0}. Semester".format(semseter)

# Alternativ: default wert für semester
def print_student(name, major, semester=1):
	print(name, "studiert", major, "im {0}. Semester".format(semseter)

print_student("chrigi", "WI") # ohne semster -> default wert
```

## Verändern von Parametern in Funktionen

Bei einem Funktionsaufruf werden die tatsächlichen Parameter als Objektreferenz übergeben.
Wenn ich also ein Objekt mitgebe und das Objekt verändere, dann persistieren die Änderungen auf im tatsächlichen Objekt.
Von primitiven Datentypen wird eine lokale Kopie erstellt.
Keine Änderungen persistieren.

Man unterscheidet zwischen veränderlichen und unveränderlichen Objekten.
Primitive Datentypen sind unveränderlich.

Wenn ich eine unveränderliche Variable erwart und die in der Funktion ändere werden die Änderungen nicht übernommen.
Wenn ich der Funktion aber ein verändeliches Objekt mitgebe schon.

In folgendem Beispiel werden Variablen auf drei verschiedene Arten überschrieben.
Die Änderung am unveränderlichen int wird nur innerhalb der funktion geschehen.
Nach der Ausführung wir die varibale den selben Wert haben wie davor.
Die veränderliche Liste lässt sich aber so verändern, das die Änderungen auch nach dem Ende der Funktion noch vorhanden sind.
Wird ein unveränderliches Objekt jedoch in einer Funktion durch ein neues ersetzt, so wird nach der Ausführung die Variable immer noch die Referenz auf das alte Zeigen.

```python
def change(f1, f2, f3):
	# unveränderlicher int wird lokal überschrieben
	f1 = 0
	# wert in verändelicher liste wird überschrieben
	f2[0] = 0
	# veränderliche Liste wird lokal komplett überschrieben
	f3 = [0]

value = 99
list1 = [99]
list2 = [99]

change(value, list1, list2)
```

## Die `return` Anweisung

- Funktion mit Rückgabe (ein oder mehrere Werte)
- Funktion ohne Rückgabe

Funktionen ohne Rückgabe geben das reservierte Wort None zurück.
Der Typ der Rückgabe muss nicht in der Funktionsdefiniton angegeben werden.
Das erlaubt "gemischte Rückgaben".

Mehrere Werte können in einem Tupel zurückgegeben werden.
Dazu muss die Anzahl der Variablen bei der Tupel-Entpackung mit der Anzalwerten im Tupel übereinstimmen.
