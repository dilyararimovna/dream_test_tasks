## Тестовое задание - Backend

Для выполнения тестового задания вам понадобится репозиторий [dream](https://github.com/deeppavlov/dream). 

Добавьте в [docker-compose.yml](https://github.com/deeppavlov/dream/blob/main/docker-compose.yml) сервис,
который получает данные любым удобным вам способом (как Telegram-бот, из брокера сообщений, через сокеты или любым другим)
и асинхронно отправляет запрос с этими данными на один из следующих сервисов:

- [badlisted-words](https://github.com/deeppavlov/dream/tree/main/annotators/BadlistedWordsDetector);
- [spacy-nounphrases](https://github.com/deeppavlov/dream/tree/main/annotators/spacy_annotator).

Оба сервиса можно запустить, выполнив команду:

```commandline
docker compose -f docker-compose.yml -f assistant_dists/dream_script_based/docker-compose.override.yml -f assistant_dists/dream_script_based/dev.yml up --build badlisted-words spacy-nounphrases
```

Результат должен отправляться по выбранному вами каналу обратно. Примеры данных для отправки вы найдёте в `test.py` этих сервисов.
Если отправка и получение данных в формате json по выбранному вами каналу вызывает затруднение, вы можете получать и отправлять в канал одно из полей payload.
Например, если сервис Dream получает данные в формате `{"a": "b"}` вы можете получать на вход вашего сервиса строку `text`,
использовать её как значение поля `"a"` и отправлять на сервис Dream `{"a": "text"}`.

Запрос и ответ сервиса должны сохраняться в базу данных (тип БД и формат хранения можете использовать любые).

Директорию с исходным кодом и докерфайлом вашего сервиса поместите в корень репозитория.
Параметры (такие как токены и т.п.) сервис должен брать из [.env](https://github.com/deeppavlov/dream/blob/main/.env) файла.
Значения добавленных вами в .env переменных следует оставить пустыми, указав лишь в README.md сервиса их назначение.

При проверке задания написанные вами сервисы будут запускаться с помощью docker-compose
(свой сервис и БД добавьте в файл [docker-compose.yml](https://github.com/deeppavlov/dream/blob/main/docker-compose.yml)).
