_AttributeError_ возникает, когда ссылка атрибута или присвоение не может быть выполнено.

Пример:

```python
class MyClass:

def __init__(self):

self.name = "Example"

obj = MyClass()

try:

print(obj.age)

except AttributeError as e:

print("Объект не имеет данного атрибута:", e)
```

Как избежать: прежде чем обращаться к атрибуту объекта, убедитесь, что этот атрибут существует. Это можно сделать с помощью функции _hasattr_.