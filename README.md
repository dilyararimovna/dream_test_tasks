#  Тестовые задания на основе DeepPavlov Dream Platform

## Задание для Software Engineer 

Выполните рефакторинг одного из двух сервисов:

- [Knowledge Grounding Service](https://github.com/deepmipt/dream/tree/dev/services/knowledge_grounding);
- [Topic Recommendation](https://github.com/deepmipt/dream/tree/dev/annotators/topic_recommendation).

Не забудьте про рефакторинг Dockerfile.

### Запуск сервисов:

```commandline
docker-compose -f docker-compose.yml -f assistant_dists/dream/docker-compose.override.yml -f assistant_dists/dream/dev.yml up --build knowledge-grounding topic-recommendation
```

### Формат решения:

Ссылка на форк репозитория или архив с файлами сервиса.
