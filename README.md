# Discord Bot: Dice Roller and Character Manager

- [English version](https://github.com/CatGaster/Dice-Discord-Bot/tree/english-version)

## Ограничение ответственности

Это неофициальный бот для Dungeons & Dragons, не связанный с Wizards of the Coast.

## Описание проекта <a name="project-description-ru"></a>

Для подробной информации о модулях бота перейдите по ссылке:

[Документация модулей бота](bot_modules/README.md)

Этот бот для Discord предназначен для помощи в настольных ролевых играх (например, Dungeons & Dragons). Он включает в себя следующие основные функции:

1. **Броски кубиков**: Поддерживаются стандартные кубики (1d2, 1d4, 1d6, 1d8, 1d12, 1d20), кастомные кубики и дополнительные кубики.
2. **Управление характеристиками персонажей**: Пользователи могут создавать и изменять свои характеристики (например, Сила, Ловкость, Мудрость и т.д.).
3. **TTS (Text-to-Speech)**: Возможность озвучивать результаты команд в голосовом чате.
4. **Удаление сообщений бота**: Возможность удалить определённок количество сообщений бота,а также автоматическое удаление сообщений бота для поддержания чистоты чата

## Структура проекта

- **`bot.py`**: Основной файл, отвечающий за запуск бота и регистрацию команд.
- **`dice.py`**: Функционал для работы с кубиками.
- **`character.py`**: Управление характеристиками персонажей.
- **`clear.py`** Удаление сообщений бота

## Создание бота для Discord
- **Чтобы создать бота для Discord, выполните следующие шаги:**

    - [Перейдите в Discord Developer Portal.](https://discord.com/developers/docs/intro)
    
    - Нажмите New Application и создайте новое приложение.
    - В меню слева выберите Bot, затем нажмите Add Bot.
    - Скопируйте Token вашего бота, он понадобится для запуска.
    - В разделе OAuth2 выберите bot в разделе SCOPES, затем установите необходимые разрешения для вашего бота в разделе BOT PERMISSIONS.
    - Полученную ссылку для приглашения бота используйте, чтобы добавить его на ваш сервер.
  

## Установка

1. Склонируйте репозиторий:

   ```bash
   git clone https://github.com/CatGaster/Dice-Discord-Bot
   cd <Dice-Discord-Bot>
   ```

2. Установите зависимости:

   ```bash
   pip install -r requirements.txt
   ```

3. Создайте файл `.env` и добавьте в него токен вашего бота:

   ```env
   DISCORD_TOKEN=<ваш токен>
   ```

4. Убедитесь, что у вас установлен Python версии 3.8 или выше.

5. Запустите бота:

   ```bash
   python bot.py
   ```

## Использование

### Команды для управления кубиками

#### `!roll_dice` или `!rd`
- Выводит кнопки для выбора кубиков.
- Поддерживаемые стандартные кубики:
  - 1d2, 1d4, 1d6, 1d8, 1d12, 1d20.
- Поддерживается кастомный кубик:
  - Введите количество граней, число бросков и дополнительные модификаторы.

#### Пример
- Бросок 1d20:
  ```
  1d20: 15
  ```
- Дополнительные кубики, например, 1d4+1d8+2d50-1d100:
  ```
  1d4 (3) + 1d8 (6) + 2d50 (20, 45) - 1d100 (65) = 9
  ```
- Учет выбранной характеристики:
  ```
  1d6 (+2 сила) = 6
  ```

#### Управление TTS
- Кнопка для включения/отключения озвучивания результатов.

### Команды для управления характеристиками

#### `!character_list` или `!cl`
- Выводит список характеристик текущего пользователя.
- Поддерживаемые характеристики:
  - Сила, Ловкость, Стойкость, Мудрость, Харизма, Интеллект.

#### Изменение характеристики
- Нажмите кнопку с характеристикой и введите новое значение.
- Пример:
  ```
  Значение Сила установлено: 15
  ```

### Команды для удаления сообщения бота

#### `!clear_bot_messages` или `!clear_bot`
- удаляет указанное количество сообщений бота
- Пример:
  ```
  !clear_bot_messages 5
  ```

## База данных

Для хранения характеристик персонажей используется SQLite. База данных создается автоматически при первом запуске и сохраняется в файле `user_stats.db`.

### Структура таблицы
- `user_id`: Идентификатор пользователя.
- `strength`: Сила.
- `dexterity`: Ловкость.
- `constitution`: Стойкость.
- `wisdom`: Мудрость.
- `charisma`: Харизма.
- `intelligence`: Интеллект.

## Зависимости

- `discord.py`: Работа с Discord API.
- `sqlite3`: Локальная база данных для хранения характеристик.
- `python-dotenv`: Для управления переменными окружения.
- `random`: Генерация случайных чисел для бросков кубиков.
- `re`: Обработка ввода для дополнительных кубиков.




## Лицензия

Проект распространяется под лицензией MIT. Для подробностей см. файл LICENSE.


---



