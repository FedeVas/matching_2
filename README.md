# Матчинг

## Что надо сделать?

Разработать алгоритм, который для всех товаров из `validation.csv` предложит несколько вариантов наиболее похожих товаров из `base.csv`;
оценить качество алгоритма по метрике `accuracy@5`.

## Использованные технологии и библиотеки

В ходе выполнения проекта использовалась библиотека FAISS для поиска ближайших соседей (KNN) на больших объемах данных. FAISS предоставляет эффективные алгоритмы для работы с поиском похожих элементов и быстрой индексацией.

Ссылка на репозиторий проекта: [Ссылка на репозиторий](https://github.com/facebookresearch/faiss/tree/main)


## Планы

В планах дальнейшего развития проекта есть намерение прикрутить модель CatBoost для улучшения качества алгоритма. CatBoost - это эффективная библиотека градиентного бустинга, которая может быть применена для решения задачи матчинга.

## Данные

- `base.csv` - анонимизированный набор товаров. Каждый товар представлен как уникальный id (0-base, 1-base, 2-base) и вектор признаков размерностью 72.
- `target.csv` - обучающий датасет. Каждая строка представляет собой один товар, для которого известен уникальный id (0-query, 1-query, …), вектор признаков и id товара из `base.csv`, который максимально похож на него (по мнению экспертов).
- `validation.csv` - датасет с товарами (уникальный id и вектор признаков), для которых необходимо найти наиболее близкие товары из `base.csv`.
- `validation_answer.csv` - правильные ответы к предыдущему файлу
