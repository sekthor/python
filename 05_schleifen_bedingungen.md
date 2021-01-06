# Schleifen und Bedindungen

Der Datentyp `bool` kann die Werte `True` oder `False` annehmen.

## Die `if` Anweisung

Der `if` Anweisung folgt ein Boolscher Ausdruck.
Ist er wahr, werden die nachfolgenden Anweisungen ausgeführt, sonst nicht.
Die `if` Bedingung endet mit mit einem `:`.
Alle Anweisungen die in der Bedingung ausgeführt werden sollen folgen auf neuen Zeilen und sind eingerückt.

```python
count = 6
if count < 10:
		print("Smaller")
```

## Boolsche Ausdrücke in Python

Folgende boolsche operatoren gibt es in Python:

```python
x == y		# x ist gleich y
x != y		# x ist ungleich y
x < y		# x ist kleiner als y
x > y		# x ist grösser als y
x <= y		# x ist kleinergleich y
x >= y		# x ist grössergleich y
and
or
not
```

Boolsche Vergleiche auf Zeichenketten basieren auf den Unicodepositionen.

```
'0' - '9' : 48 - 57
'A' - 'Z' : 65 - 90
'a' - 'b' : 97 - 122
```

```
"M" < "N"
"N" > "M"
"Max" > "Mal"
"Ma " < "Max"
```

## Die `ìf-else` Anweisung

```python
if count <= MAX
	count += 1
else:
	count = 0
```

```python
if condition:
	do_stuff()
elif condition2:
	do_alternate()
else:
	do_in_all_other_cases()
```

## Die `while` Schleife

```python
while count <= 3:
	print(count)
	count += 1
```

## `break` und `continue`

Mit `break` wird die Schleife umgehend abgebrochen. `continue` hingegen bricht nur den aktuellen Durchlauf der Schleife ab und geht zur nächsten Iteration über.

## `else` in Schleifen

Schleifen können eine `else` Bedingung enthalten.
Wenn der boolsche Ausdruck in der Bedingung der Schleife nicht wahr ist, wird das else ausgführt.
Wird die Schleife aber durch ein `break` beendet wird das `else` **nicht** ausgeführt.

```python
while count < 3:
	count += 1
else:
	print("done")
```
