Medical Insurance Cost Prediction - CP1

Описание проекта
Предсказание годовых медицинских расходов на основе демографических данных, показателей здоровья, образа жизни и страховой информации.
Тип задачи: регрессия.

Датасет
Источник: Kaggle - Medical Insurance Cost Prediction
Автор: Mohan Krishna Thalla
Ссылка: https://www.kaggle.com/datasets/mohankrishnathalla/medical-insurance-cost-prediction
Тип на Kaggle: Monetary
Количество строк: 100 000
Исходное количество колонок: 54
Количество колонок после Feature Engineering: 62
Целевая переменная: annual_medical_cost (годовые медицинские расходы)

Причины выбора датасета
- Monetary тип (целевая переменная денежная)
- Достаточный объем данных для обучения
- 54 признака для анализа
- Наличие пропусков требует предобработки
- Не является Getting Started
- Практическая ценность задачи

Выполненные задачи CP1

1. Обработка и подготовка данных
- Загрузка данных и первичный анализ
- Выявлены пропуски в колонке alcohol_freq (30 083 значения)
- Пропуски обработаны: создана колонка alcohol_freq_known с категорией 'Unknown'
- Дубликаты отсутствуют
- Выявлено 6 772 выброса в целевой переменной (6.77%)
- Выбросы обработаны методом winsorization
- Категориальные признаки приведены к типу category
- Создано 7 новых признаков
- Выполнен корреляционный анализ
- Разделение данных: Train 70%, Val 15%, Test 15%
- Проведен анализ на data leak

2. Созданные признаки
- age_group: возрастные категории (6 групп)
- bmi_category: категории ИМТ по стандарту ВОЗ
- cost_to_income_ratio: отношение расходов к доходу
- chronic_disease_count: количество хронических заболеваний
- total_claims_value: общая сумма страховых выплат
- smoker_chronic_interaction: взаимодействие курения с болезнями
- mean_arterial_pressure: среднее артериальное давление

3. Моделирование
Baseline модель: Linear Regression на исходных данных (без Feature Engineering)
Результаты:
- RMSE: $626.55
- MAE: $322.13
- R²: 0.9601

4. Метрики качества
- RMSE (основная): штрафует большие ошибки, интерпретируема в долларах
- MAE (вспомогательная): устойчива к выбросам
- R² (дополнительная): доля объясненной дисперсии

Fixed Seed
RANDOM_SEED = 42

Структура проекта
- cp1_data_preprocessing.ipynb - основной ноутбук
- medical_insurance.csv - исходные данные
- medical_insurance_processed.csv - обработанные данные
- X_train.csv, X_val.csv, X_test.csv - признаки
- y_train.csv, y_val.csv, y_test.csv - целевая переменная
- README.md - описание проекта
- requirements.txt - зависимости

Запуск проекта
pip install -r requirements.txt
jupyter notebook cp1_data_preprocessing.ipynb

Автор: Katushka1144