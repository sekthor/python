# Listen, Bereiche, Tupel

## Listen

Listen sind dynamische Mengen.
Im Gegensatz zu Java kann eine List verschiedene Datentypen enthalten.

```python
names = ["Christian", "Hans", "Jakob"]
liste = ["Hallo", 27, 1.3435] 
```

Auf die Elemente einer Liste kann mit Indices zugegriffen werden.
Hier funktionieren auch die Slicing Operationen.

```python
l = [1,2,3,4]
l[2]	 # Element an pos 2
l[-1	 # letztes Element
l[1:3]	 # element 1-3
```

Beim Slicing sieht die Reihenfolge so aus:

```python
liste[start:end:step]
```

Methoden die auf Listen aufgerufen werden können:

```python
list.append("element")
list.insert(i,x) 	# füge x an stelle i hinzu
list.remove(x)		# lösche element x
list.pop()		# pop letztes element
list.clear()
list.index(x[, start[, end]]) # index von x, optinal start, end
list.count(x)		# Zähle anz x
list.sort()		# Sortiere Liste
```

## Bereiche (Range)

Die Funktion `range()` definiert einen Bereich.

```python
range(5)	# 0,1,2,3,4
range(5,10)	# 5,6,7,8,9
range(0,10,3)	# 0,3,6,9 (dreier Schritte)
range(-10,-100,-30) # -10,-40,-70 (-30er Schritte)
```

Ein range-Objekt ist keine Liste.
Es kann aber mit der `list()` Funktion in eine Liste umgewandelt werden.

```python
list(range(4))
```

Mit `len()` kann ich die Länge einer Liste (Anz. Elemente) herausfinden.

## Die for-Anweisung

Die for Anweisung kann über die Elemenete einer Sequenz iterieren.
Dabei wird eine Variable definiert, der in jedem Durchgang das aktuelle Element der Sequenz zugewiesen wird.

```python
values = [1, 2, 3]
for val in values:
	print(val)
```

Dabei kann auch Bereich mit `range()` verwendet werden.

```python
for val in range(1, 4):
	print(val)
```

### List Comprehensions

List Comprehensions werden verwendet um aus bestehenden Listen neue Listen zu machen.
Dabei wird oft eine Form einer Transformation auf die Werte angewendet.
Ein primitives Beispiel wäre:

```python
squares = []
for x in range(10):
	squares.append(x**2)
```

Eine elegantere Schreibweise ist, die Anweisung direkt zwischen eckige Klammern zu schreiben.
Es wird so eine neue Liste zurückgegeben.

```python
squares = [x**2 for x in range(10)]
```

Man kann so also auch Kopien von Listen anfertigen und im gleichen Schritt die neue Liste tranformieren.

```python
vec = [-4, -2, 0, 2, 4]

[x*2 for x in vec]

# Nur die positiven
[x for x in vec if x >= 0]

# Eine funktion mit der Zielvariable als Prameter aufrufen
[abs(x) for x in vec]

# eine Methode auf allen Elementen aufrufen
[f.upper() for f in list_of_strings]

# Eine Liste von Tupeln defnieren
[(x, x**2) for x in range(6)]
[(0, 0), (1, 1), (2, 4), (3, 9), (4, 16), (5, 25)]
```

## Zweidimensionale Listen

Liste besteht aus Listen.
Kann als Tabelle betrachtet werden.

```python
students = [["Joe", "Kim"], ["Sam", "Sue"], ["Kelly", "Chris"]]
name = students[2][1]
```

## Kopieren von Listen

Eine Variable einer anderen zu zuweiesen würde in Aliassen resultieren.
Die Liste soll also kopiert werden, wenn Sie unabhängig verwendet werden soll.

```python
# Möglichkeit 1: Kopieren mit for
list1 = [1, 2, 3, 4]
list2 = []
for i in range(len(list1)):
	list2.append(list1[i])

# Möglichkeit 2: Kopieren mit Slicing
list1 = [1, 2, 3, 4]
list2 = list1[:]

# mit dem Modul Copy
import copy
list1 = [1, 2, 3, 4]
list2 = copy.copy(list1)
```

## Tupel

Ein Tupel besteht wie eine Liste aus einer Anzahl von Werten.
Es gibt folgende Möglichkeiten eine Tupel zu definieren:

- leerer Tupel `()`
- Trennen durch Komma `(a,b,c)`
- Trennen durch Komma ohne Klammer `a,b,c`
- Konvertierung mit
  - `tuple([1,2,3])` -> `(1,2,3)`
  - `tuple("abc")` -> `('a','b','c')`

Tupel sind **unveränderlich**.
Sie müssen entpackt werden um auf die elemente zuzugreifen.

```python
t = 12345, 54321, "Hallo!"

# mit index zugreifen
t[1]

# Länge des Tupels
len(t)

# Index eines Elements
t.index(54321)
```

Einen Tupel entpacken:

```python
a, b, c = t
```
