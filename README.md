# RU: Репозиторий проектов в области Data Science: Анализ и прогнозирование количества заказов на такси

### Данный проект создан в рамках курса Яндекс Практикум: DataScience

Курс предоставил данные для анализа и обучения моделей. Репозиторий состоит из двух файлов: HTML-версии проектного файла и Jupyter Notebook (.ipynb) версии.

## Основной функционал, реализованный в проекте:
- Декомпозиция временного ряда: остаток, сезонность, тренд
- Модели: Ridge, Lasso, DecisionTreeRegressor, LGBMRegressor, RandomForestRegressor

## Используемые библиотеки:
- seaborn
- numpy
- matplotlib
- pandas
- statsmodels
- sklearn
- lightgbm

## Задачи проекта:

### Основная задача:
Создание модели, которая сможет прогнозировать количество заказов такси на следующий час.

### Требование к модели:
Значение метрики RMSE на тестовой выборке не должно превышать 48.

### В рамках проекта необходимо сделать:
1. Загрузить данные и выполнить их ресемплирование по одному часовому интервалу.
2. Проанализировать данные.
3. Обучить разные модели с различными гиперпараметрами. Сделать тестовую выборку размером 10% от исходных данных.
4. Проверить данные на тестовой выборке и сделать выводы.

### В ходе проекта были выполнены следующие шаги:
- Первичный анализ данных:
    - Проанализированы пропуски и дубликаты: отстутствуют
    - Произведена замена индекса на столбец `datetime`, сортировка индекса по возрастанию и ресемплированы данные с заменой временного промежутка на 1 час. Для анализа данные с марта до августа 2018 года включительно
- Анализ сезонности и тренда:
    - были построены графики сезонности, тренда и остатков. Проанализирована сезонность в течение дня и выдвинута гипотеза о причине повышенного спроса. Сезонность в данных - 1 день
    - Для прогнозирования был создан датафрейм с дополнительными признаками - временными задержками. Лучшие результаты RMSE на кол-ве lags = 24.
    - Данные были разделены и подготовлены к обучению моделей
    - Общий тренд данных - увеличение кол-ва заказов с каждым месяцем - функция тренда возрастающая. Это может быть связано как с увеличением проходимости аэропорта - большее количество самолетов, так и с длительными отпусками всей семьей - гораздо удобнее вызвать такси, чем кого-то просить забрать с аэропорта.
- Обучение моделей:
    - Для рассмотрения были выбраны модели: LGBMRegressor, RandomForestRegressor, Ridge, Lasso, DecisionTreeRegressor
    - Модели для тестирования были выбраны по параметру RMSE на кроссвалидации, а также времени обучения модели. Для дальнейшего тестирования была отобрана LGBMRegressor
- Тестирование моделей:
    - Для финального решения были построены графики визуализации предсказаний и расчет RMSE на тестовых данных. Лучшей моделью была выбрана LGBMRegressor, основываясь на ее результатах на тренировочных данных, а также времени обучения
    - Результат финально выбранной модели удовлетворяет условиям отбора < 48

## Автор:

- Тарасова Ульяна
- telegram: [talurana](https://t.me/talurana)
- email: tarasova.ulya@gmail.com
- github: [talurana](https://github.com/talurana)

# ENG: DataScience project repository: Taxi Order Predictions

### This project was created as part of the Yandex Practicum course.

The course provided data for analysis and model training. The repository consists of two files: an HTML version of the project file and a Jupyter Notebook (.ipynb) version.

## Important features used in this project:
- Seasonal Decomposition: Residual, Seasonal, Trend
- Models: Ridge, Lasso, DecisionTreeRegressor, LGBMRegressor, RandomForestRegressor

## Used libraries in project:
- seaborn
- numpy
- matplotlib
- pandas
- statsmodels
- sklearn
- lightgbm

## Tasks:

### **Main task:** 
Create a model that can predict the number of cabs in the next hour.

### Model Requirement:
The value of the **RMSE** metric on the test sample should not exceed 48.

### Project Methodology:
1. Load the data and resample it one hour interval at a time.
2. Analyze the data.
3. Train different models with different hyperparameters. Make a test sample of size 10% of the original data.
4. Validate the data on the test sample and draw conclusions.

### The following steps were accomplished during the project:
- Primary data analysis:
    - Analyzed omissions and duplicates: absent
    - Replaced the index with the `datetime` column, sorted the index in ascending order, and resampled the data with the time period replaced with 1 hour. For the analysis, the data from March to August 2018 inclusive
- Seasonality and trend analysis:
    - Seasonality, trend and residuals were plotted. Seasonality during the day was analyzed and hypothesized the cause of increased demand. The seasonality in the data is 1 day
    - A dataframe with additional features - time lags - was created for forecasting. The best RMSE results on the number of lags = 24.
    - The data was split and prepared for model training
    - The general trend of the data is an increase in the number of orders with each month - the trend function is increasing. This may be due to both increased airport traffic - more planes, and long family vacations - it is much more convenient to call a cab than to ask someone to pick up from the airport.
- Model Training:
    - The models selected for consideration were LGBMRegressor, RandomForestRegressor, Ridge, Lasso, and DecisionTreeRegressor
    - The models for testing were selected based on the RMSE parameter on cross validation as well as model training time. LGBMRegressor was selected for further testing
- Model Testing:
    - Prediction visualization plots and RMSE calculation on the test data were plotted for the final decision. The best model was selected as LGBMRegressor based on its results on the training data as well as training time
    - The result of the final selected model satisfies the selection conditions < 48

## Author:

- Tarasova Uliana
- telegram: [talurana](https://t.me/talurana)
- email: tarasova.ulya@gmail.com
- github: [talurana](https://github.com/talurana)