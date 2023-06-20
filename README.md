## Скрипт для прогрева ваших Твиттеров, которые импортированны в ферму AdsPower
Все понимают, что Твиттеры нужно греть. Я периодически прогреваю свои акки и за 8 месяцев у меня отлетело всего 4 штуки (покупал их по USD 0.12). Этот скрипт поможет сэкономить тебе бешенное количество времени и немного денег. Он работает с профилями Twitter, которые импортированны в [AdsPower](https://share.adspower.net/Btc9YYgpiyJxhmW).

Связь с создателем: https://t.me/CrytoBusher <br>
Если ты больше по Твиттеру: https://twitter.com/CryptoBusher <br>

Залетай сюда, чтоб не пропускать дропы подобных скриптов: https://t.me/CryptoKiddiesClub <br>
И сюда, чтоб общаться с крутыми ребятами: https://t.me/CryptoKiddiesChat <br>

## 🔥 Последние обновления
- [x] 20.06.2023 - Добавлена функция подписки на рандомные аккаунты из базы <br>
- [x] 20.06.2023 - Добавлена функция подписки на обязательные аккаунты из списка <br>
- [x] 20.06.2023 - Обновлен сценарий, добавлена рандомизация всех видов активностей <br>
- [x] 20.06.2023 - Скрипт теперь проверяет, открыт ли профиль пользователем, если открыт - может его скипнуть или прогреть <br>

## Функции
1. Постинг твитов
2. Подписка на рандомные аккаунты из списка
3. Подписка на все аккаунты, указанные как обязательные

## Преимущества
1. Рандомизация координат, по которым производится клик по кнопке.
2. Рандомизация ввода текста в поле для твита.
3. Рандомизация других задержек.
4. Рандомизация последовательности выполнения разного вида активностей
5. Работа через AdsPower.
6. Отчетность в виде скриншотов.
7. Проверка статуса профиля (открыт / закрыт), настройка работы с кейсом, когда профиль уже открыт пользователем (пропустить, прогреть)

## Недостатки
1. Однопоточность.
2. Нет проверки случайно появившихся модалок (смена почты, включение уведомлений). Когда поймаю их - подправлю.

## Логика работы
1. Рандомно выбирается профиль AdsPower.
2. Запускается сценарий прогрева согласно настройкам
   1. Проверка статуса профиля (открыт / закрыт). Если профиль уже открыт - производится либо прогрев либо пропуск (в зависимости от настроек)
   2. Запуск профиля, если он был закрыт
   3. Рандомизация активностей (твит, рандомные подписки, обязательные подписки)
   4. Производятся все активности, которые выбраны пользователем, согласно рандомному порядку
   5. Закрытие профиля, если он не был ранее открыт. Если профиль уже был открыт - он не закрывается
3. Повтор с новым профилем

## Первый запуск
1. Устанавливаем Python 3.10.
2. Качаем репозиторий.
3. Открываем терминал, переходим в папку с файлами и пишем команду "pip install -r requirements.txt".
4. Открываем файл "data/config.py" с помощью любого текстового редактора и подбиваем настройки рандомизации. Все пояснения по настройкам описаны в комментариях в самом файле.
5. Открываем файл "data/profile_ids.py" с помощью любого текстового редактора и забиваем свои профиля как в примере ("название":"ID из AdsPower").
6. Открываем файл "data/tweets.txt" и закидываем базу твитов. Нагенерить можно самому, на фрилансе или в ChatGPT. Чем меньше твитов - тем чаще они будут повторяться, тк они выбираются рандомом.
7. Открываем файл "data/twitter_handles.txt" и забиваем туда свои Twitter Username, так, чтоб они соответствовали аккаунтам, вбитым в файл "data/profile_ids.py". Да, это гемор и не было в этом необходимости сейчас, но это пригодится в дальнейшем, когда я буду добавлять новые фичи.
8. Открываем файл "data/random_users_to_follow" и забиваем туда юзернеймы аккаунтов (без @). Это будет база для рандомных подписок.
9. В терминале, находясь в папке проекта, вписываем команду "python3 adspower_twitter_warmup.py" и жмем ENTER.
