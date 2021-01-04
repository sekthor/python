# Weitere Datenstrukturen

## Stapel und Schlangen

Der Stapel ist eine lineare Datenstruktur.
Er ist aufgebaut wie eine Liste, mit dem Unterschied, dass Elemente nur ans Ende angehängt werden können und Elemente nur vom Ende der Liste entfernt werden können.
Es kann nicht via Index zugegriffen werden.
Man hat nur auf das Letzte Element Zugriff.
LIFO-Prinzip.
Push, Pop Operationen.
Peek erlaut den Zugriff auf das letzte Element, ohne dieses zu entfernen.

In Python lassen sich Listen wie stacks verwenden.
Die push Operation wäre `append()` und die pop Operation heisst `pop()`.

Eine Schlange verwendet das FIFO Prinzip.
In Python kann eine Schlange.
Push und Pop ist in einer Liste sehr einfach.
In Python ist eine `deque` implementiert.
Sie verwendet ebenfalls die `append` methode um neue Elemente hinten in die Schlange einzureihen.
Um Elemente aus der Schlange zu entfernen kann die `popleft()` methode verwendet werden.

```python
from collections import deque

queue = deque(["Eric", "John", "Michael"])

queue.append("Graham")
queue.popleft()
```

## Mengen und Wörterbücher

Mengen enthalten keine Duplikate.
Das Testen mit `in` ist sehr schnell in Mengen.
Ein Set kann wiefolgt definiert werden:
Mengen sind selber veränderbar, dürfen aber keine veränderbaren Objekte enthalten.
Es gibt kein Reihenfolge und daher keine Indexierung und kein Slicing.

```python
my_set = {1,2,3}
```

Um ein Leeres Set zu erstellen muss die Methode `my_set = set()` verwendet werden, da `{}` ein leeres Wörterbuch und nicht ein Set erstellen würde.

Elemente können mit `discard()` oder mit `remove()` entfernt werden.
Der einzige Unterschied ist, dass remove einen Fehler wirft, wenn das Element nicht vorhanden ist.
Discard kann damit umgehen.

Um zwei Mengen zu vereinigen kann der `|` Operator oder die `union()` methode verwendet werden.
Die Schnittmenge kann durch `&` oder `intersection()` erstellt werden.
Für die Differenz kann `-` oder `difference()` verwendet werden.

Boolean Methoden für Mengen:

- `B.isdisjoint(A)`: Keine Überschneidung
- `B.issubset(A)`: Ist B Teil von A
- `B.issuperset(A)`: Ist A Teil von B

Bei **Wörterbüchern** verläuft die Indexierung über einen Schlüsselwert.
Bei einer Liste wäre das die Positionsindexierung.
Das Wörterbuch speichert Key-Value Paare.

```python
dict([('sape', 4139),('guido', 4127)])
```

Der Zugriff auf einen Vaule erfolgt mit dem Schlüssel als Index.

```python
my_dict[key] = value
value = my_dict[key]
```

Alternativ kann auch die `get(key)` methode verwenden.
Diese wirft keinen Error, wenn es den Key gar nicht gibt.

Um Elemente zu entfernen kann die `pop(key)` verwendet werden.


