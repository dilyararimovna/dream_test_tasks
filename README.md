#  Тестовые задания на основе DeepPavlov Dream Platform

## Задание для Software Engineer 

### Задание 1

Для выполнения тестового задания вам понадобится репозиторий [dream](https://github.com/deepmipt/dream). 

Добавьте в [docker-compose.yml](https://github.com/deepmipt/dream/blob/dev/docker-compose.yml) сервис, который получает данные любым удобным вам способом (как Telegram-бот, из брокера сообщений, через сокеты или любым другим) и асинхронно отправляет запрос с этими данными в любой из сервисов:

- [Knowledge Grounding Service](https://github.com/deepmipt/dream/tree/dev/services/knowledge_grounding);
- [Topic Recommendation](https://github.com/deepmipt/dream/tree/dev/annotators/topic_recommendation).

Оба сервиса можно запустить выполнив команду:

```commandline
docker-compose -f docker-compose.yml -f assistant_dists/dream/docker-compose.override.yml -f assistant_dists/dream/dev.yml up --build knowledge-grounding topic-recommendation
```

Результат должен отправляться по выбранному вами каналу обратно. Примеры данных для отправки вы найдёте в `test.py` этих сервисов. Если отправка и получение данных в формате json по выбранному вами каналу вызывает затруднение, вы можете получать и отправлять в канал одно из полей payload. Например, если сервис Dream получает данные в формате `{"a": "b"}` вы можете получать на вход вашего сервиса строку `text` и использовать её как значение по ключу `"a"` и отправлять на сервис Dream `{"a": "text"}`.

Директорию с исходным кодом и докерфайлом вашего сервиса поместите в корень репозитория. Параметры (такие как токены и т.п.) сервис должен брать из [.env](https://github.com/deepmipt/dream/blob/dev/.env) файла. Значения добавленных вами в .env переменных следует оставить пустыми, указав лишь в README.md сервиса их назначение.

При проверке задания написанный вами и оптимизированный сервисы будут запускаться с помощью docker-compose. Если для работы вашего сервиса понадобится дополнительный сервис (например, с базой данных), добавьте его в [docker-compose.yml](https://github.com/deepmipt/dream/blob/dev/docker-compose.yml) и он тоже будет запущен.

### Задание 2 (опциональное)

Выполните рефакторинг [Knowledge Grounding Service](https://github.com/deepmipt/dream/tree/dev/services/knowledge_grounding) или [Topic Recommendation](https://github.com/deepmipt/dream/tree/dev/annotators/topic_recommendation). Рефакторинг может включать в себя:

- Замену Flask на FastAPI, использование Pydantic при работе с пэйлоадом.
- Использование модуля `unittest` для тестов.
- Изменение форматирования кода или файловой структуры.

Всё вышеперечисленное является лишь примером. Мы не определяем минимальный объём изменений и просим привести сервис к виду, который бы вы посчитали приемлемым при публикации кода в opensource.

Не забудьте про оптимизацию Dockerfile.

### Формат решения:

Ссылка на форк репозитория или архив с файлами сервисов.
