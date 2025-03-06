Язык программирования Python реализует как стандартное одиночное наследование:

```python
class Mammal():
    className = 'Mammal'

class Dog(Mammal):
    species = 'Canis lupus'

dog = Dog()
dog.className # Mammal
```

так и множественное:

```python
class Horse():
    isHorse = True

class Donkey():
    isDonkey = True

class Mule(Horse, Donkey):
mule = Mule()
mule.isHorse # True
mule.isDonkey # True
```

Используя [множественное наследования](https://ru.wikipedia.org/wiki/%D0%9C%D0%BD%D0%BE%D0%B6%D0%B5%D1%81%D1%82%D0%B2%D0%B5%D0%BD%D0%BD%D0%BE%D0%B5_%D0%BD%D0%B0%D1%81%D0%BB%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5) можно создавать классы-миксины (примеси), представляющие собой определенную особенность поведения. Такой микси можно "примешать" к любому классу.

[[Python/Python]]
[[OOP]]
[[Principles]]