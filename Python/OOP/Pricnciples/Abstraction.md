Кроме наследования, существует и другой [~~способ организации межклассового взаимодействия~~](https://metanit.com/sharp/patterns/1.2.php) – ассоциация (агрегация или композиция), при которой один класс является полем другого.

Пример композиции:

```python
class Salary:
    def __init__(self,pay):
        self.pay = pay

    def getTotal(self):
        return (self.pay*12)

class Employee:
    def __init__(self,pay,bonus):
        self.pay = pay
        self.bonus = bonus
        self.salary = Salary(self.pay)

    def annualSalary(self):
        return "Total: " + str(self.salary.getTotal() + self.bonus)

employee = Employee(100,10)
print(employee.annualSalary())
```

Пример агрегации:

```python
class Salary(object):
    def __init__(self, pay):
        self.pay = pay

    def getTotal(self):
        return (self.pay * 12)

class Employee(object):
    def __init__(self, pay, bonus):
        self.pay = pay
        self.bonus = bonus

    def annualSalary(self):
        return "Total: " + str(self.pay.getTotal() + self.bonus)

salary = Salary(100)
employee = Employee(salary, 10)
print(employee.annualSalary())
```

Ассоциированные объекты могут [циклически ссылаться](https://ru.wikipedia.org/w/index.php?title=%D0%A6%D0%B8%D0%BA%D0%BB%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B0%D1%8F_%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0&action=edit&redlink=1) друг на друга, что ломает стандартный механизм сборки мусора. Избежать подобных проблем при ассоциации помогают слабые ссылки (модуль `weakref`).

[[Python/Python]]
[[OOP]]
[[Principles]]