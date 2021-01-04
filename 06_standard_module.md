# Standardmodule

Anders als bei der Java API sind die Standardfunktionen von Python nicht in Klassen, sondern in Module aufgeteilt.

Es gibt eingebaute Funktionen.
Sie sind nicht Teil der Standardmodule, sondern sind bereits in den Interpreter eingebaut.

Module lassen sich mit dem `import` Befehl importieren.

```python
import math
math.sqrt(2)
```

Die Module können umbenannt werden um sie zu verwenden.

```python
import math as m
```

## Das Modul `random`

Zufällig Zahlen brauchen einen seed.
Als Default wird die Systemzeit genommen.
Wenn ich Experimente wiederholen will, kann ich den `random.seed(x)` selber bestimmen.

```python
import random

# Zufällige Zahl zwischen a und b
random.randint(a,b)

# Zufällige ganze Zahl ohne die Obergrenze b
# step:
random.rangrange(a,b[, step])

# Zufällige Gleikommazahl zwischen 0 und 1
random.random()

# Zufällige Gleitkommazahl zwischen a und b
random.uniform(a,b)

# Normalverteilte Zufallszahl mit Mittelwert mu und Standardabweichung sigma
random.gauss(mu, sigma)

# Liste mischen
random.shuffle(x)

# Zufälliges Element aus Liste
random.choice(x)

# Zufällige Stichprobe der Grösse k aus Liste x
# ACHTUNG: k muss mit namen angegeben werden
# sample(x, k=3)
random.sample(x,k)
```

## Das Modul `Math`

```python
import math

# aufrunden
math.ceil(x)

# abrunden
math.floor(x)

# Anz Möglichkeiten k Elemente aus n Elementen zu wählen ohne Reihenfolge
math.comb(n,k)

# Anz Möglichkeiten k Elemente aus n Elementen zu wählen mit Reihenfolge
math.perm(n, k)

# Absolutwert
math.fabs(x)

# Eulersche zahl hoch x
math.exp(x)

# logarithmus von x zu basis base
math.log(x[, base])

# x hoch y als gleitkommazal
# für genaue integers ** operator verwenden
math.pow(x,y)

# quadrat wurzel
math.sqrt(x)

# Trigonometrie
math.cos(x)
math.sin(x)
math.tan(x)
math.acos(x)
math.asin(x)
math.atan(x)

# Konstanten
math.pi
math.e
math.inf
-math.inf
```

## Dateien lesen und schreiben

Folgende Module erleichtern den Umgang mit Dateien:

- csv: Umgang mit CSV Dateien
- gzip: Komprimierung
- linecache: Direktzugriff auf Zeilen einer Datei
- shutil: Dateioperationen auf höherer Ebenen (bsp Kopieren)
- ...

Einfaches lesen funktionier mit der Eingebauten funktion `open()`.
Parameter sind der Dateipfad und der Modus.
Modi sind:

- `'r'`: read only
- `'w'`: write
- `'a'`: append
- `'r+'`: lesen und schreiben erlaubt

```python
file.object = open(name, mode)

# lese ohne size = bis ende des files
file.object.read([size])

# bis ende Zeile lesen
file.object.readline()

# Zeile für Zeile iterieren
for line in file.object:
	print(line)

```

Es lohnt sich anstatt `file = open("file.txt")` das reservierte wort `with` zu verwenden.
Damit wird sichergestellt, das die Datei am Ende des Programs ordnungsgemäss geschlossen wird.

```python
with open("file.txt") as file:
	# Do something with "file"
```
### Datei schreiben

```python
import datetime

with open("protocol.txt", "a") as protocol_file:
	now = str(datetime.datetime.now())
	protocol_file.write("Programm gestartet um: " + now + "\n")
```

## Webbrowser

Das Modul Webbrowser unterstützt das öffnen von URLs im Webbrowser-

```python
import webbrowser

url = "http://google.com")
webbrowser.open(url)
webbrowser.open_new_tab(url)
```

## Das Modul statistics

```python
import statistics

# Median. Bei Ordinaler Skallierung median_low oder median_high verwenden
statistics.median(data)

# Modus: häufigster Datenpunkt
statistics.mode(data)

# Liste der häufigsten Werte
statistics.multimode(data)

# Varianz der Population
statistics.pvariance(data)

# Standardabweichung der Population
statistics.pstdev(data)

# varianz und sd von Stichprobe
statistics.variance(data)
statistics.stdev(data)

# Quantile nach anzahl gewünschter Qunatile
# Für Quartile also n=4
statistics.data, n=x)
```

## Externe Module

Neben den Standard Modulen lassen sich auch Drittpartei Module verwenden.
Die Module finden sich in ![pypi.org](https://pypi.org).
Populäre Beispiele sind:

- Python Imaging Library (PIL): Bildverarbeitung
- Matplotlib: Grafikfunktionen
- SciPy: Wissenschaftliche Berechnungen
- Django: Web Entwicklung

Installieren kann man diese Module mit `pip`.

```
pip install matplotlib
```

## Das Modul Matplotlib

```python
import matplotlib.pyplot as plt

# liste von x und von y koordinaten
# marker legt fest wie der Datenpunkt aussieht
# o : punkt
# * : stern
# D : diamant
# ^ : dreieck
plt.plot(x_coords, y_coords[, marker='o']

# Beschriftung
plt.title("titel")
plt.xlabel("X-Achse")
plt.ylabel("Y-Achse")

# Raster
plt.grid(true)

# Achsen Grenze festlegen
plt.xlim(xmin=0, xmax=10)
plt.ylim(ymin=0, ymax=10)

# Beschriftung Ticks auf Achse
plt.yticks(tick_list, name_list)
plt.yticks(tick_list, name_list)

# Balkendiagramm
# Color darf mehrere farben haben: color=("r","b")
plt.bar(x_coords, heights[, bar_width, color=t])
