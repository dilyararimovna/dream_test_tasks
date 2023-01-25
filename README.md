#  Тестовые задания на основе DeepPavlov Dream Platform

## Задание для Software Engineer 

Вопросы можете задавать в Telegram `ignatovf`.

### Задание

Для выполнения тестового задания вам понадобится репозиторий [dream](https://github.com/deeppavlov/dream). 

Выполните рефакторинг [Knowledge Grounding Service](https://github.com/deeppavlov/dream/tree/dev/services/knowledge_grounding). Рефакторинг может включать в себя:

- Замену Flask на FastAPI, использование Pydantic при работе с пэйлоадом.
- Использование модуля `unittest` для тестов.
- Изменение форматирования кода или файловой структуры.
- Оптимизацию докерфайла.

Всё вышеперечисленное является лишь примером. Мы не определяем минимальный объём изменений и просим привести сервис к виду, который бы вы посчитали приемлемым при публикации кода в opensource.

Сервис можно запустить с помощью команды

```commandline
docker-compose -f docker-compose.yml -f assistant_dists/dream/docker-compose.override.yml -f assistant_dists/dream/dev.yml up --build knowledge-grounding
```


Не забудьте про оптимизацию Dockerfile.

### Формат решения:

Ссылка на форк репозитория или архив с файлами сервисов.
