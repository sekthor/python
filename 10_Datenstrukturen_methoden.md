# Datenstrukturen

## Stapel (Stack)

```python
stack = [1,2,3]
stack.append(4)
stack.pop()
```

## Schlangen (Deque)

```python
from collections import deque
queue = deque([1,2,3])
queue.append(4)
queue.popleft()
list(queue)		# queue wieder zu liste umwandeln
```

## Menge (Set)

```python
# set definieren
my_set = {1,3}
my_set = set() # my_set = {} -> dictionary
my_set = set([1,2,3])
my_set = "helloworld" # 'h','o', ...

# hinzufügen
my_set.add(4)			# 1 Element
my_set.update([5,6,7])	# mehrere Elemente (Liste)
my_set.update({5,6,7})  # mehrere Elemente (Tupel)
my_set.update([1,2], {3,4}) # mehrere Elem (mehrere Parameter)

# löschen
my_set.remove(2)	# Error wenn nicht vorhanden, kein return
my_set.discard(2)	# Kein Error wenn nicht vorhanden, kein return
my_set.pop()		# zufällig, da ungeordnet, return element
my_set.clear()		# alle elemente löschen

# vereinigen
my_set.union(other_set)			# Vereinigung
my_set | other_set				# Vereinigung
my_set.intersection(other_set)	# Schnittmenge
my_set & other_set				# Schnittmenge
my_set.difference(other_set)	# Differenz
my_set - other_set				# Differenz

# boolean
my_set.isdisjoint(other_set)	# Hat keine gemeinsamen E?
my_set.issubset(other_set)		# ist in other_set enthalten?
my_set.issuperset(other_set)	# enthält other_set?
```

## Wörterbücher (Dictionary)

```python
# erstellen
my_dict = {}
my_dict = {1:"apple",2:"ball"}
my_dict = {"name":"john","nr":1234}
my_dict = dict([(1,"hallo"),(2,"welt")])
my_dict = {x: x**2 for x in (2,4,6)} # {2:4,4:16,6:36}

# einfügen
my_dict[key] = value
#zugriff
value = my_dict[key]
value = my_dict.get(key) # None type, wenn nicht vorhanden

# entfernen
my_dict.pop(key)	# return value
my_dict.popitem()	# beliebiges item
my_dict.clear()		# alle items
del my_dict[key]

# boolean
key in my_dict

# listen
my_dict.items() # liste aller items
my_dict.keys()	# liste aller keys
```


