# Разработка системы для автоматического анализа и категоризации электронных писем: классификация по типу запросов или содержанию
## Принцип работы
Проект целенаправлен на создание системы, способной автоматически анализировать и классифицировать электронные письма на основе их содержания или других характеристик. Эта система может быть полезна для фильтрации спама, автоматической сортировки электронных писем или дополнительного анализа текстовых данных в корпоративной или личной почте.

Данные взяты из датасета в Kaggle https://www.kaggle.com/datasets/mandygu/lingspam-dataset и загружены в GitHub под названием 'messages.csv'

В коде загружаются необходимые библиотеки. Проводится предобработка текста: объединение столбцов 'subject' и 'message' в один столбец 'text'. Разделение на обучающий и тестовый наборы для оценки модели. Используются метод опорных векторов (SVM) с ядром 'linear' в качестве классификатора текста. Для векторизации текста используется TF-IDF (Term Frequency-Inverse Document Frequency). В конце сохраняется обученная модель с использованием библиотеки joblib.

Далее для использования обученной модели загружается ранее обученная модель из файла. Задается текст нового электронного письма, который нужно классифицировать. Проводится предобработка текста нового письма, включая токенизацию и удаление стоп-слов. И выводится результат классификации на экран.
## Запуск кода
Скачайте данные. Добавьте в 'Файлы' в Google Colab. Переименуйте путь к файлу в загрузках данных, если потребуется.

Или перейдите в Google Colab через файл кода в GitHub.

## Примечательные моменты
1. Применяется метод опорных векторов (SVM) с ядром 'linear' для решения задачи бинарной классификации спама и не спама.
SVM является мощным алгоритмом машинного обучения, эффективным для работы с различными видами данных, включая текст.
2. Применение метода TF-IDF для векторизации текста. TF-IDF (Term Frequency-Inverse Document Frequency) используется для оценки важности слов в документе относительно всего корпуса текстов.
3. Методы естественного языка (NLP), такие как токенизация и предобработка текста, для адекватной обработки текстовых данных.
4. Joblib используется для сохранения обученной модели в первом коде и для загрузки модели во втором коде. Это обеспечивает сохранение времени, так как не требуется повторное обучение модели.

## Результаты
![Alt-текст](Result.png )
