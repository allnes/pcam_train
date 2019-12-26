**ПРАКТИЧЕСКАЯ РАБОТА №2**


**РАЗРАБОТКА ПОЛНОСТЬЮ СВЯЗАННЫХ НЕЙРОННЫХ СЕТЕЙ**


Разработана полносвязная нейронная сеть FCNN с использованием библиотеки глубокого обучения Keras для решения задачи бинарной классификации. Проведены эксперименты с разным количеством скрытых слоев и числом скрытых элементов на каждом слое. Собраны результаты качества работы сети.

### 1. Разработанные скрипты.
Реализация в скрипте *pcam_fcn.ipynb*

### 2. Тестовые конфигурации сетей.
- With the same layers

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/lab2.png?raw=true)

- With dropout

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/lab2_dropout.png?raw=true)

- Without dropout

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/lab2_wth_dropout.png?raw=true)

### 3. Предобработка данных.

Было произведено изменение размерности данных с [96, 96, 3] к [32, 32, 3].

### 4. Результаты экспериментов.


|   |  TRAIN WITH THE SAME LAYERS | TRAIN WITH DROPOUT | TRAIN WITHOUT DROPOUT | VALID WITH THE SAME LAYERS | VALID WITH DROPOUT | VALID WITHOUT DROPOUT | TEST WITH THE SAME LAYERS | TEST WITH DROPOUT | TEST WITHOUT DROPOUT |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
| ACCURACY   | 76.2062  | 68.5176 | 75.4093 | 75.1037  | 68.2586 | 73.1414 | 72.9492  | 67.2637 | 70.6939 |
| PRECISION  | 77.699  | 62.914 | 77.1441 |  78.7681 | 63.3524 | 77.5079 | 76.9573  | 62.9622 | 75.0926 |
| RECALL | 73.5115  | 90.2137 | 72.2137 | 68.6724  | 86.51 | 65.1353 | 65.482  | 83.7882 | 61.8916 |
|  F1-SCORE | 75.5472  | 74.1303 | 74.5975 |  73.3746 | 73.1358 | 70.785 | 70.7574  | 71.8975 | 67.856 |
| INFERENCE TIME |  25sec | 24sec | 23sec | 3sec | 3sec | 3sec |  3sec | 3sec | 3sec |
| TRAIN TIME | 22min | - | - | 22min | - | - | 22min | - | - |



- With the same layers

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/fcnn_result_1.PNG?raw=true)


- With dropout

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/fcnn_result_2.PNG?raw=true)


- Without dropout

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/fcnn_result_3.png?raw=true)
