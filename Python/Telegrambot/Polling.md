[[Telegrambot]]

По сути, на одном из предыдущих шагов, когда мы с вами писали программу, которая опрашивает сервер Telegram на наличие апдейтов для бота, мы реализовали polling, то есть постоянный опрос сервера. Его суть в том, что идет обращение к серверу, сервер что-то отвечает и сразу закрывает соединение. При этом не важно, есть апдейты или нет

Вот так может выглядеть polling со стороны клиента, то есть нашего бота (**не забудьте вместо токена моего бота вставить токен вашего бота**):

```python
import requests
import time


API_URL = 'https://api.telegram.org/bot'
BOT_TOKEN = '5424991242:AAGwomxQz1p46bRi_2m3V7kvJlt5RjK9xr0'

offset = -2
updates: dict


def do_something() -> None:
    print('Был апдейт')


while True: 
    start_time = time.time()
    updates = requests.get(f'{API_URL}{BOT_TOKEN}/getUpdates?offset={offset + 1}').json()

    if updates['result']:
        for result in updates['result']:
            offset = result['update_id']
            do_something()

    time.sleep(3)
    end_time = time.time()
    print(f'Время между запросами к Telegram Bot API: {end_time - start_time}')
```

Вот так это выглядит в терминале:

```no-highlight
Время между запросами к Telegram Bot API: 3.149364948272705
Время между запросами к Telegram Bot API: 3.1524858474731445
Время между запросами к Telegram Bot API: 3.1554458141326904
Был апдейт
Время между запросами к Telegram Bot API: 3.1923599243164062
Время между запросами к Telegram Bot API: 3.145864963531494
Время между запросами к Telegram Bot API: 3.137209892272949
Время между запросами к Telegram Bot API: 3.1353447437286377
Был апдейт
Время между запросами к Telegram Bot API: 3.152209997177124
Время между запросами к Telegram Bot API: 3.1605660915374756
Время между запросами к Telegram Bot API: 3.150103807449341
```

