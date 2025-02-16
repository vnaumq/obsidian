Scope - это область видимости Python, которая определяет доступность переменных внутри блока кода.

Есть две области видимости переменных:

- Глобальная - переменная обьявлена вне функции
- Локальная - переменная обьявлена внутри функции

Чтобы задать глобальную переменную внутри функции нужно дописать global
**Чтобы задать переменную в внутренюю функцию, которая передается и в внешнюю функцию нужно дописать nonlocal**

```python
config = { 'language': 'ru', 'timezone': 'UTC' }

def get_config(key):
	def inner():
		 return config.get(key, None)
	 return inner
	 
get_language = get_config('language') get_timezone = get_config('timezone') print(get_language()) # ru print(get_timezone()) # UTC
```
