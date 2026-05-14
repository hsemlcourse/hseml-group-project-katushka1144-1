# Medical Insurance Cost Prediction - CP2

**Студент:** Круковская Екатерина Петровна

## Описание задачи

Тип задачи: регрессия.
Цель: предсказать годовые медицинские расходы (annual_medical_cost).
Метрики: RMSE (основная), MAE, R².
Датасет: Medical Insurance Cost Prediction (Kaggle).
## Структура проекта

- cp1_data_preprocessing.ipynb - обработка данных
- cp2_modeling.ipynb - моделирование
- medical_insurance.csv - исходные данные
- medical_insurance_processed.csv - обработанные данные
- X_train.csv, X_val.csv, X_test.csv - сплиты признаков
- y_train.csv, y_val.csv, y_test.csv - сплиты целевой переменной
- requirements.txt - зависимости
- pyproject.toml - конфигурация проекта
- Dockerfile - Docker контейнер
- .gitignore - игнорируемые файлы
- README.md - описание проекта

## Запуск проекта

git clone https://github.com/hsemlcourse/hseml-group-project-katushka1144-1.git
cd hseml-group-project-katushka1144-1
pip install -r requirements.txt
jupyter notebook cp2_modeling.ipynb


## Результаты CP2

Сравнение моделей:

| Модель | RMSE | MAE | R² |
|--------|------|-----|-----|
| Linear Regression (Baseline) | $626.55 | $322.13 | 0.9601 |
| Ridge  ----------------------| $626.55 | $322.08 | 0.9601 |
| Lasso  ----------------------| $626.69 | $320.66 | 0.9601 |
| Random Forest ---------------| $194.70 | $11.53 | 0.9961 |
| XGBoost ---------------------| $564.42 | $57.81 | 0.9676 |
| LightGBM --------------------| $533.39 | $50.61 | 0.9711 |
| Voting Regressor ------------| $389.20 | $32.72 | 0.9846 |
| Stacking Regressor --------- | $195.71 | $12.03 | 0.9961 |

Уменьшение размерности (PCA):
Random Forest после PCA показал R² = 0.9960.

Финальная модель: Random Forest
Параметры: n_estimators=100, max_depth=20, min_samples_split=2, min_samples_leaf=2
Результат: R² = 0.9961

## Fixed Seed

RANDOM_SEED = 42

## Выводы

Random Forest показал лучший результат. Ансамбли близки к нему. Линейные модели не улучшили baseline. PCA не ухудшил качество.

## Ссылка

https://github.com/hsemlcourse/hseml-group-project-katushka1144-1/tree/cp2
