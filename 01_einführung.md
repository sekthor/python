# Python Kurs

## Vorlesung 1

Ein Python Programm wird aus Modulen aufgebaut. Ein Modul ist nicht das gleiche wie eine Klasse.
In einem Modul können Funktionen, Variablen, Klassen usw definiert werden.
Eine Funktion ist keine Methode. Es wird kein Objekt benötigt um sie aufzurufen.
Ähnlich wie eine Statische Methode.

```python
# so wird eine Funktion definiert
def quote_of_steve():
	print("Steve Jobs:")
	print("Es ist besser, ein Pirat zu sein, als der Marine beizutreten")

# so wird eine Funktion aufgerufen
quote_of_steve()
```

Die Einrückung ist zentraler Bestandteil der Syntax.
Es gibt keine geschweifte Klammern um einen Methodenrumpf einzufassen.
Stattdessen wird eine Ebene mehr eingerückt.

### Programmierungsarten

**imperativ:** Anweisungen werden in der Reihenfolge an den Rechner übergeben, in der sie ausgeführt werden sollen.

**prozedual:** Erweitert imperative Programmierung mit der Idee mehrere Anweisungen unter einem bestimmten Bezeichner zusammenzufassen.

**Objekt-Orientiert:** Abbildung von Strukturen der abzubildenden Welt in Objekte.

### Schlüsselworte

```python
False       await       else        import      pass
None        break       except      in          raise
True        class       finally     is          return
and         continue    for         lambda      try
as          def         from        nonlocal    while
assert      del         global      not         with
async       elif        if          or          yield
```

### Konventionen

- Pakete: lowercase
- Module: lowercase
- Klassen: CamelCase
- Funktionen: lower_case_with_underscore
- Konstaten: UPPER_CASE_WITH_UNDERSCORE
