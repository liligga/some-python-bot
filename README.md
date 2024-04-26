## Сделать бота для телеграма

В боте есть два экземпляра класса Router:

- один для ответа пользователю на все текстовые сообщения
- второй для запуска опроса пользователя, можно сделать так, чтобы опрос начинался при команде `/start`

##### Важное

Склонировать этот репозиторий можно при помощи следующих команд:

```shell
git clone https://github.com/liligga/python40-bot.git
cd python40-bot
git remote remove origin
```

Последняя команда важна! Она упростит загрузку завершенного проекта в Ваш(!) личный репозиторий.

### Echo router

Бот должен принимать текстовые сообщения от пользователя и отвечать на них следующим образом:

- `'Hello, World!'` превращается в `'World! Hello,`
- `'1 2 3'` превращается в `'3 2 1'`
- `'Иван Иванов'` превращается в `'Иванов Иван'`

т.е. бот отвечает на сообщение пользователя сообщением, в котором слова идут в обратном порядке

### Survey router

Это роутер для прохождения опроса пользователем. Бот должен принимать сообщения от пользователя и запрашивать следующие данные:

- имя(name)
- возраст(age)
- род занятий(occupation)
- заработная плата или оценка(salary_or_grade)

Если пользователь отвечает на вопрос о возрасте больше 18 лет, то на 4-м вопросе следует спросить об заработной плате,
если 18 и меньше, то спросить о средней оценке в школе(в реальном проекте такие разные данные сохранять в одну колонку в БД не стоит)

На последнем шаге бот должен сохранять собранные данные в базу данных.

Можно также сделать проверку возраста, если младше 7 или старше 60, то можно завершать опрос.

### База данных

В файле `database.py` уже все подготовлено для работы с базой данных SQLite в асинхронном стиле.
А файл `queries.py` не заполнен до конца, там надо написать запрос для создания таблицы для данных из опроса.

### Допольнительно

Есть маленькие детали, про которые здесь не упомянуто, но без них бот работать не будет, или будет работать неправильно.
Важное:

- токен бота не должен быть в коде
- база данных не должна попасть на github

Завершенный код бота нужно загрузить на Github, в отдельный(ваш, не мой) репозиторий и ссылку скинуть в google forms.
