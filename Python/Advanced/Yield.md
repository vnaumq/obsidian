Другой способ создать [[Генератор]] — использовать функцию генератора. Мы берём ключевое слово yield, чтобы вернуть generator в функции.

```python
def file_reader(file_path):
	for row in open(file_path, "r"):
		yield row
for row in file_reader('./demo.txt'):
	print(row)
```
