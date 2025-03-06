Концепция полиморфизма – важная часть ООП на Python. Все методы в языке изначально [виртуальные](https://ru.wikipedia.org/wiki/%D0%92%D0%B8%D1%80%D1%82%D1%83%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9_%D0%BC%D0%B5%D1%82%D0%BE%D0%B4). Это значит, что дочерние классы могут их переопределять и решать одну и ту же задачу разными путями, а конкретная реализация будет выбрана только во время исполнения программы. Такие классы называют полиморфными.

```python
class Mammal:
    def move(self):
        print('Двигается')

class Hare(Mammal):
    def move(self):
        print('Прыгает')

animal = Mammal()
animal.move() # Двигается
hare = Hare()
hare.move() # Прыгает
```

[[Python/Python]]
[[OOP]]
[[Principles]]