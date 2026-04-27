# Предсказание цен автомобилей — линейная регрессия

Учебный проект: модель линейной регрессии для предсказания цены автомобиля (MSRP) с оценкой качества относительно наивного baseline.

## Признаки

`Year`, `Engine HP`, `Engine Cylinders`, `highway MPG`, `city mpg`, `Popularity` → целевая переменная `MSRP`.

## Запуск

```bash
pip install pandas scikit-learn
python car_price_regression.py
```

```python
from car_price_regression import car_price_regression
car_price_regression("data.csv")
```

## Результаты

| Модель             | RMSE      |
|--------------------|-----------|
| Линейная регрессия | 45 817.49 |
| Глупая модель      | 61 673.47 |
| Разница            | 15 855.98 |

Линейная регрессия снижает ошибку относительно baseline примерно на 26%.

## Детали реализации

- Пропуски заполняются средним значением по столбцу (`fillna`)
- Разбивка выборки: 75% / 25%, `random_state=42`
- Метрика качества: RMSE (`root_mean_squared_error` из sklearn)
- Глупая модель предсказывает среднее значение `y_train` для всех объектов
