 **PCAM DATASET AND TRAIN MODEL**

------------



**ЛАБОРАТОРНЫЕ РАБОТЫ ПО КУРСУ**


**«МЕТОДЫ ГЛУБОКОГО ОБУЧЕНИЯ ДЛЯ РЕШЕНИЯ ЗАДАЧ КОМПЬЮТЕРНОГО ЗРЕНИЯ».**

Цель данной лабораторной работы - с помощью нейронных сетей реализовать решение задачи бинарной классификации.



##  1.  Постановка задачи.

Имеются входные данные. Вычисляем выход сети $$Z$$. Также существует ожидаемый выход сети $$Y$$. Необходимо минимизировать функцию ошибки $$E(Y, Z)$$.

### Функции активации:

#### На скрытом слое

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/ReLU.PNG?raw=true)


#### На выходном слое


![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/sigmoid.png?raw=true)


### Функция ошибки 

Бинарная кросс-энтропия

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/loss.png?raw=true)

### Обучение на тренировочной выборке
Сеть обучаем определенное количество эпох, то есть полностью проходим по тестовой выборке и делим данные на пакеты.

1. Инициализация весов
2. В каждой эпохе:

- Перемешивание выборки

- Пакетное использование данных

- Корректировка весов по алгоритму обратного распространения ошибки


## 2. Тренировочные и тестовые наборы данных.
В работе используются данные из https://github.com/basveeling/pcam, полученные из гистопатологических сканирований срезов лимфатических узлов. Каждое изображение помечено двоичной меткой, указывающей на наличие метастатической ткани. Зеленые прямоугольники указывают на опухолевую ткань в центральной области, что указывает на положительную метку.
> Пример изображений.

![](https://github.com/basveeling/pcam/blob/master/pcam.jpg?raw=true)



Общее количество - 327680 цветных изображений размером
w \* h \* c  = 96 \* 96 \* 3.

|  Данные  | Количество примеров |
| ------------ | ------------ |
|  train  |  262.144 |
|  test  |  32.768  |
|  valid  | 32.768  |





## 3. Метрика качества решения задачи.
 
Y - оригинал
U - наш классификатор

|   | Y = TRUE |  Y = FALSE |
| ------------ | ------------ | ------------ |
|  **U = TRUE** |  True Pos  |  False Pos |
|  **U = FALSE** |  False Neg  |  True Neg  |





![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/metric_accuracy.png?raw=true) - точность классификатора, где

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/metric_N.png?raw=true) 

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/metric_precision.png?raw=true)  - качество классификатора

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/metric_recall.png?raw=true)  - полнота классификатора

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/metric_f1_score.png?raw=true) 




## 4. Исходный формат хранения данных. 
Формат хранения данных следующий: 

`train_x_name = 'camelyonpatch_level_2_split_train_x.h5'`
`train_y_name = 'camelyonpatch_level_2_split_train_y.h5'`

`test_x_name = 'camelyonpatch_level_2_split_test_x.h5'`
`test_y_name = 'camelyonpatch_level_2_split_test_y.h5'`

`valid_x_name = 'camelyonpatch_level_2_split_valid_x.h5'`
`valid_y_name = 'camelyonpatch_level_2_split_valid_y.h5'`

`meta_train_name = 'camelyonpatch_level_2_split_train_meta.csv'`
`meta_valid_name = 'camelyonpatch_level_2_split_valid_meta.csv'`
`meta_test_name  = 'camelyonpatch_level_2_split_test_meta.csv'`




## 5. Формат, в котором данные предоставляются на вход сети.
Данные необходимо предобработать. Изменим размер до 32 \* 32 \* 3 и представим в виде вектора размерностью (32,32, 3), также нормируем значения в нем.



## Реализация
### Внешние зависимости

google.colab - соединяет с Google Drive

tensorflow - backend Keras

keras - основной фреймворк для работы с нейронными сетями

gzip - разархивация данных

shutil - обработка файлов и данных

pandas - анализ данных

matplotlib  - для визуализации

cv2 - изменение размера изображений

numpy - для работы с векторами и матрицами

keras_metrics - метрики