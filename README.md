#  Тестовые задания на основе DeepPavlov Dream Platform

## Задание для Software Engineer 

Выполните рефакторинг одного из двух сервисов:

- [Knowledge Grounding Service](https://github.com/deepmipt/dream/tree/dev/services/knowledge_grounding);
- [Topic Recommendation](https://github.com/deepmipt/dream/tree/dev/annotators/topic_recommendation).

Рефакторинг может включать в себя:

- Замену Flask на FastAPI, использование Pydantic при работе с пэйлоадом.
- Использование модуля `unittest` для тестов.
- Изменение форматирования кода или файловой структуры.

Всё вышеперечисленное является лишь примером. Мы не определяем минимальный объём изменений и просим привести сервис к виду, который бы вы посчитали приемлемым при публикации кода в opensource.

Не забудьте про оптимизацию Dockerfile.

Добавьте в [docker-compose.yml](https://github.com/deepmipt/dream/blob/dev/docker-compose.yml) сервис, который получает данные любым удобным вам способом (как Telegram-бот, из брокера сообщений, через сокеты или любым другим) и асинхронно отправляет запрос с этими данными на оптимизированный сервис. Результат должен отправляться по выбранному вами каналу обратно.

Директорию с исходным кодом и докерфайлом вашего сервиса поместите в корень репозитория. Параметры (такие как токены и т.п.) сервис должен брать из [.env](https://github.com/deepmipt/dream/blob/dev/.env) файла.

При проверке задания написанный вами и оптимизированный сервисы будут запускаться с помощью docker-compose. Если для работы вашего сервиса понадобится допольнительный сервис (например с базой данных), добавьте его в [docker-compose.yml](https://github.com/deepmipt/dream/blob/dev/docker-compose.yml) и он тоже будет запущен.

### Запуск сервисов:

```commandline
docker-compose -f docker-compose.yml -f assistant_dists/dream/docker-compose.override.yml -f assistant_dists/dream/dev.yml up --build knowledge-grounding topic-recommendation
```

### Формат решения:

Ссылка на форк репозитория или архив с файлами сервисов.
