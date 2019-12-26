**ПРАКТИЧЕСКАЯ РАБОТА №5**


**ПЕРЕНОС ОБУЧЕНИЯ ГЛУБОКИХ НЕЙРОННЫХ СЕТЕЙ**

Применен перенос обучения для решения задачи, поставленной в ходе второй практической работы. Проведены эксперименты с сетями, существующими для решения классических задач. Собраны результаты качества работы сетей с предварительной настройкой весов.


### 1. Разработанные скрипты.

Реализация в скриптах *pcam_lab_5_train_pretrain_model.ipynb*, *pcam_lab_5_train_resnet50.ipynb*

### 2. Тестовые конфигурации сетей.

- Взята претренированная модель MobileNet на данных ImageNet, были удалены полносвязные слои и проводилась тренировка новых собственных полносвязных слоев и дотренировка весов претренированной модели MobileNet.


![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/model_plot_pretrain_mobilenet.png?raw=true)


- Взята модель ResNet50 и полностью обучена заново.


![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/model_plot_train_resnet50.png?raw=true)


### 3. Результаты экспериментов.

|   |  TRAIN MOBILENET | TRAIN RESNET50 | VALID MOBILENET | VALID RESNET50 |  TEST MOBILENET | TEST RESNET50 |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
| ACCURACY   | 95.3144 | 75.6752 | 86.6088 | 63.6169 | 80.7403 | 64.9688 |
| PRECISION  | 95.3144 | 75.6752 | 86.6088 | 63.6169 | 80.7403 |  64.9688 |
| RECALL | 92.0262 | 98.5445 | 88.8766 | 96.507 | 87.9276 | 96.5058 |
|  F1-SCORE | 99.2263 | 52.1202 | 83.6642 | 28.1874 | 71.2462 | 31.0313 |
| INFERENCE TIME | 105sec | 100sec | 25sec | 25sec | 13sec | 13sec |
| TRAIN TIME | 42min | - | - | 56min | - | - |


- ImageNet


![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/model_plot_pretrain_mobilenet_loss_bin_acc.png?raw=true)
![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/model_plot_pretrain_mobilenet_prec_recall.png?raw=true)
![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/model_plot_pretrain_mobilenet_f1score.png?raw=true)


- ResNet50


![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/model_plot_train_resnet50_loss_bin_acc.png?raw=true)
![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/model_plot_train_resnet50_prec_recall.png?raw=true)
![](https://github.com/NovozhilovaA/pcam_train/blob/master/images/model_plot_train_resnet50_f1score.png?raw=true)



