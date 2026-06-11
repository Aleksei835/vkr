# Восстановление базы данных PostgreSQL

Дамп БД: dump.sql

# Способ 1: Через командную строку (быстрее всего)
1. Создать пустую БД (если ещё не создана)
```createdb -U postgres my_database```

2. Восстановить дамп
```psql -U postgres -d my_database -f database.sql```

Если нужно перезаписать существующую БД:
```
dropdb -U postgres my_database
createdb -U postgres my_database
psql -U postgres -d my_database -f database.sql
```

# Способ 2: Через pgAdmin
Откройте pgAdmin
Нажмите правой кнопкой на Databases → Create → Database
Задайте имя (например, my_database)
Нажмите правой кнопкой на созданной БД → Restore...
В поле Filename выберите dump.sql
Нажмите Restore

Альтернативный путь (если Restore не работает):
Откройте Query Tool (иконка молнии или Tools → Query Tool)
Перетащите файл dump.sql в окно запроса
Нажмите Execute (F5)

# Способ 3: Через DBeaver
Подключитесь к PostgreSQL (хост: localhost, порт: 5432, пользователь: postgres)
Нажмите правой кнопкой на соединение → Tools → Execute Script
Выберите файл dump.sql
Нажмите Execute (или Ctrl+Shift+E)
Альтернативно:
Откройте dump.sql в DBeaver (File → Open)
Выберите целевое соединение в выпадающем списке сверху
Нажмите Execute SQL Script (или Ctrl+X)

# Способ 4: Через DataGrip / IntelliJ IDEA
Подключитесь к PostgreSQL
Нажмите правой кнопкой на схеме (обычно public) → Run SQL Script...
Выберите dump.sql
Нажмите Run
