* 12.2019
1. Complete the study of the thesis；
- Paper: [PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation](https://arxiv.org/abs/1612.00593)
- [Project page](http://stanford.edu/~rqi/pointnet/)
- [Author's implementation](https://github.com/charlesq34/pointnet)
2. Complete the tasks on HNP; 

    Completed and displayed on the wiki page：
    [MyWiki page](https://github.com/Yansz/BKP_3D-Seg-Pointnet/wiki)

3. Complete a small segmentation case.

* 01.2020
1. Write a program that implements the algorithm in the paper;
2. Train the model and test it on the dataset;
3. Try to optimize the problems of the algorithm, such as modifying the position of T-net;

* 02.2020
1. Я закончил исследовательский отчет по глубокому обучению в облаке точек и отправил его в MOEVMPPS-2020;
2. Я провел обучение и тестирование сети Pointnet на основе графического процессора платформы Google Colab 
и завершил классификацию облаков точек по набору данных ModelNet 40 и по сегментации сегментов на наборе данных Shapenet.

* 03.2020
1. Я начну писать теоретические части первых нескольких глав моей дипломной работы;
2. Я найду доступные ресурсы графических процессоров для обучения и тестирования наборов данных больших облачных точек сцены.

- 04.2020

1. Завершил теоретическую часть первых двух глав статьи, начал внедрять PointNet в PyTorch и продолжал использовать Google Cloud Platform для обучения и тестирования.
2. Разработка модели оптимизации с учетом PointNet—MSS-PointNet.
3. Журналы тренировок сохраняются в [Google Cloud Disk](https://drive.google.com/drive/folders/1fc1Tg1d8nW36dGyH3KU6LJpMt97vS08d?usp=sharing)

* 05.2020

1. Кодирование реализует MSS-PointNet и проводит эксперимент управления, проводит тест на точность.
2. Продолжать улучшать остальную часть BKP, завершен бизнес-план для этого проекта.
3. Подготовить дипломные защитные слайды и другие сопутствующие материалы.



## Results of pytorch implementation

### Test in Area_5

![tensorboard area5](/02.PointNet_pytorch/img/all.png)

## Meshlab visualization(obj files)

![prediction example](/02.PointNet_pytorch/img/area5-cr1.png)

![prediction example](/02.PointNet_pytorch/img/area5-lobby1.png)