**ПРАКТИЧЕСКАЯ РАБОТА №2**


**РАЗРАБОТКА ПОЛНОСТЬЮ СВЯЗАННЫХ НЕЙРОННЫХ СЕТЕЙ**


Разработана полносвязная нейронная сеть FCNN с использованием библиотеки глубокого обучения Keras для решения задачи бинарной классификации. Проведены эксперименты с разным количеством скрытых слоев и числом скрытых элементов на каждом слое. Собраны результаты качества работы сети.

### 1. Разработанные скрипты.
Реализация в скрипте *pcam_fcn.ipynb*
### 2. Тестовые конфигурации сетей.
- With the same layers

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/fcnn_1.PNG?raw=true)

- With dropout

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/fcnn_2.PNG?raw=true)

- Without dropout

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/fcnn_3.PNG?raw=true)

### 3. Результаты экспериментов.
- With the same layers

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/fcnn_result_1.PNG?raw=true)

|   |  TRAIN  | VALID   | TEST   |
| ------------ | ------------ | ------------ | ------------ |
| ACCURACY   | 76.2062  | 75.1037  | 72.9492  |
| PRECISION  | 77.699  |  78.7681 | 76.9573  |
| RECALL | 73.5115  | 68.6724  | 65.482  |
|  F1-SCORE | 75.5472  |  73.3746 | 70.7574  |
|  TIME  |  25s 97us/step  | 3s 95us/step  |  3s 95us/step |


- With dropout

![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/fcnn_result_2.PNG?raw=true)

|   |  TRAIN  | VALID   | TEST   |
| ------------ | ------------ | ------------ | ------------ |
| ACCURACY   | 68.5176  | 68.2586  |  67.2637 |
| PRECISION  | 62.914  | 63.3524  | 62.9622  |
| RECALL | 90.2137  | 86.51 |  83.7882 |
|  F1-SCORE | 74.1303  |  73.1358 |  71.8975 |
|  TIME  |  24s 90us/step  | 3s 89us/step  |  3s 89us/step |

- Without dropout


![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/fcnn_result_3.png?raw=true)


|   |  TRAIN  | VALID   | TEST   |
| ------------ | ------------ | ------------ | ------------ |
| ACCURACY   | 75.4093 | 73.1414| 70.6939  |
| PRECISION  | 77.1441  | 77.5079  | 75.0926  |
| RECALL | 72.2137  |  65.1353 | 61.8916  |
|  F1-SCORE |  74.5975 | 70.785 |  67.856 |
|  TIME  | 23s 89us/step |  3s 87us/step | 3s 86us/step  |