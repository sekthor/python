# Objektorientierung

Alles in Python ist ein Objekt.
Jetzt sollen eigene Objekte erstellt werden.

## Einfache Klassen programmieren

Für eine Klasse wird typischerweise eine Datei mit dem gleichen Namen erstellt.
Das ist nicht vorgeschrieben, aber Konvention.
Jede Datei ist ein Modul.
Ein Modul kann Klassen enthalten.

Eine leere Klasse in Python wird mit dem reservierten Wort `class` dem Namen der Klasse und einem `:`- definiert.
Eine Klasse darf nicht leer sein.

```python
class Book:
	pass
```

Um ein Objekt zu instanzieren, wird der 'Konstruktor' aufgerufen.

```python
book1 = Book()
```

Instanzvariablen einer Klasse müssen direkt im Konstruktor definiert werden.
Der Konstruktor initialisiert die Daten eines Objektes.
In Python kann die Methode `__init__` als Konstruktor bezeichnet werden.

```python
class Book:
	# Konsturktor
	def __init__(self):
		pass
```

Genau genommen gibt es keinen Konstruktor.
Das Objekt wied automatisch erzeugt.
`__init__` initialisiert das Objekt lediglich.
Die Methode muss immer mindestens einen Parameter `self` haben.
Der erste Parameter ist also immer `self`.
Die self Variable referenziert das aktuellei Objekt.
Der self parameter muss beim aufruf nicht mitgegeben werden.
Das passiert automatisch.

Eine Instanzvariable (bsp title) wird innerhalb des Konstruktors deklariert und definiert (gleicher Schritt).
`self.title = "Titel"`.

```python
class Book:
	# Konsturktor
	def __init__(self, pages, title):
		self.pages = pages
		self.title = title
```

Es gibt keine Sichtbarkeitsmodifikatoren public oder private.

Als Äquivalent der `toString()` Methode aus Java kann in Python eine `__str__` methode definiert werden.

```python
class Book:
	# Konsturktor
	def __init__(self, pages, title):
		...

	def __str__(self):
		return self.title + " " + str(self.pages)
```

Jede Objektmethode muss als erster Parameter `self` entgegen nehmen.

Das Überladen von Methoden ist in Python **nicht Möglich**.
Die obere Methode wird von der unteren überschrieben.
Es können aber auch hier Defaultwerte verwendet werden.

```python
class Country:
	def __init__(self, name="Switzerland"):
		self.name = name
```

## Konstanten und Statische Variablen

In Python gibt es keine echten Konstanten.
Es gibt aber ein Paar Konventionen um Variablen wie Konstanten zu verwenden.

- Name ausschliesslich Grossbuchstaben, wörter durch `_` getrennt
- Es lohnt sich ein modul `constants.py` zu definieren, in dem alle Konstanten definiert sind.

Variablen die im Klassenrumpf definiert werden sind automatisch Klassenvariablen.
Klassenvariablen werden von allen Instanzen einer Klasse geteilt.
Sie sind also statisch.

Wenn ich eine Klassenvariable überschreibe, sollte ich das so tun: `Klassenname.variable = "neu"`.
Wenn ich eine Klassenvariable über eine Objektreferenz ändern möchte, geht das nicht.
Es wird stattdessen eine neue Insantzvariable erschaffen.

```python
class Dog:
	kind = "Hund"
	def __init__(self, alter)
		self.alter = alter

dog1 = Dog(3)

# Klassenvariable überschreiben
Dog.kind = "Dog"

# Neue Instanzvariable!!!
dog1.kind = "Dog"
```

Zusammenfassend:

- Es gibt nur einen Konstruktor
- Instanzvariablen sind direkt im Konstruktor definiert
- Man kann Parametern Standardwerte zuweisen
- Jede Instatnzmethode benötigt `self` als ersten Parameter
- Rückgabetyp muss nicht definiert werden

## Sichtbarkeit: Getter und Setter

Python hat keine Sichtbarkeitsmodifikatoren wie Java es mit `public`, `private` und `protected`.
Es ist grundsätzlich alles public.
Um die Sichtbarkeit zu modifizieren können underscores verwendet werden.

- Der einfache `_` kann eine Variable von einem Schlüsselwort unterscheiden: `float_ = 8`
- Wenn `_` als Beginn des Variablennames verwendet wird, ist diese Variable gekennzeichnet als privater Kontext, auch wenn man tatsächlich immer noch darauf zugreifen kann.
- Der Dopplete Understrich "Dunder" (`__`) macht die Variable tatsächlich privat.
- Den Dunder vor UND nach der Variable zeigt an dass es sich um eine spezielle Methode handelt.

In Python ist es bad-practise private Instanzvariablen mit gettern und settern zu holen.
Instanzvariablen die ausserhalb verwendet werden sollen public sein.

```python
# Bad practise
# So sollte in Python nicht programmiert werden
class P:
	def __init__(self,x):
		self.__x = x
	
	def get_x(self):
		return self.__x

	def set_x(self, x):
		self.__x = x
```

Das Problem ohne Setter ist, dass das Element der Kontrolle wegfällt.
Da auf die Variable zugegriffen werden kann, können auch ungültige Werte gesetzt werden.
Um dieses Problem zu lösen kann man mit Decorators arbeiten.

```python
class P:
	def __init__(self,x):
		self.__x = x

	# Python äquivalent zum getter
	# Methode muss gleich heissen wie Variable
	@property
	def x(self):
		# Zusätzlicher Code hier möglich
		return self.__x

	# python setter
	@x.setter 
	def x(self,x):
		# code zur Kontrolle
		self.__x = x
```

Jedes Mal wenn `objekt.x = ...` gesetzt wird, wird die setter Methode verwendet.
So auch im Konsturktor.

## Vererbung in Python

Was in Java mit `extends` geregelt wird funktioniert in Python so.

```python
class Person:
	def__init__(self, name):
		self.name = name
	def __str__(self):
		return self.name

class Student(Person):
	def __init__(self, name, major):
		super().__init__(name)
		self.major = major
	def __str__(self):
		super().__str__() + " sutdiert " + self.major
```

Es gibt die eingebauten funktionen `isinstance()` und `issubclass()` die im Kontext der Vererbung verwendet werden können.

```python
isinstance(p1, Person) # True
issubclass(Person, Student) # True
```

## Mehrfachvererbung

Im Gegensatz zu Java erlaubt Python die Mehrfachvererbung.
Probleme, die bei der Mehrfachvererbung können sein:

- Die beiden Superklassen haben Methoden die gleich heissen. Python handelt einen solchen Konflikt so, dass die Methode der ersten Klasse verwendet wird. Also jener, die zuerst in der erbenden Klasse gennant wird: `class Child(Parent1, Parent2)`.

```python
class LandAnimal():
	def walk(self):
		print("gehen")

class WaterAnimal():
	def swim(self):
		print("Schwimmen")

class Amphibian(LandAnimal, WaterAnimal):
	pass
```

## Enums in Python

Enums sind Aufzählungen die an eindeutige, konstante Werte gebunden sind.
Ein Enum wird in Python wie eine Klasse definiert und muss von der Klasse Enum erben.
Die Werte des Enums werden durch den Bezeichner und eine Zuweisung eines "Indexes" definiert.

```python
from enum import Enum

class Currency(Enum):
	CHF = 1
	EUR = 2
	USD = 3
```

Auf die Elemente können dann wie auf Klassenvariablen zugegriffen werden.

```python
c1 = Currency.CHF
c1.name  # CHF
c1.value # 1
```

Strings können in Aufzählungsobjekte wiefolgt verwandelt werden.

```python
c3 = Currency["CHF"]
```

Mit einer `for` Schleife kann über alle Werte eines Enums iteriert werden.

```python
for currency in Currency:
	print(currency.name)
```
