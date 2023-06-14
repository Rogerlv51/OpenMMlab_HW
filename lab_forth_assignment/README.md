## 第四次作业说明

- **本次作业难度不大，不过有几个坑点，一个是ann_dir中有两张图需要我们手动修改下命名，因为和img_dir对不上，另外特别注意修改DubaiDataset配置文件的类别数，以及对应的colorbar，当然由于我们这次采用西瓜数据集的话，本身也就只有6个类，所以照猫画虎即可。此外最好对之前子豪兄的数据集和配置文件进行重新命名，包括所有的类、数据集绑定、路径等等可避免一切意外发生**

- **以下是文件列表详细说明**

    - train_log： 训练日志
    - test_log： 测试日志
    - MMSegentation.ipynb： 实验训练和测试脚本（注：由于在colab上多次运行，所以可能看到有些命令行没有运行的情况，忽略即可）
    - pspnet-WatermelonDataset_20230613.py：本次实验的配置文件
    - WatermelonDataset.py：数据集初始定义
    - `_init_.py`：数据集初始绑定文件
    - test.png：测试网络图片
    - pred.jpg：网图预测结果

- **以下是详细实验结果说明**

    - **训练日志**
        ```shell
        2023/06/13 14:03:51 - mmengine - INFO - Iter(val) [11/11]    aAcc: 87.9000  mIoU: 51.3200  mAcc: 59.1200  data_time: 0.0203  time: 0.4532
        2023/06/13 14:03:51 - mmengine - INFO - The previous best checkpoint /content/mmsegmentation/work_dirs/WatermelonDataset/best_aAcc_iter_800.pth is removed
        2023/06/13 14:03:52 - mmengine - INFO - The best checkpoint with 87.9000 aAcc at 1600 iter is saved to best_aAcc_iter_1600.pth.
        2023/06/13 14:04:55 - mmengine - INFO - Iter(train) [1700/2000]  lr: 9.6207e-03  eta: 0:02:56  time: 0.5850  data_time: 0.0178  memory: 3979  loss: 0.0454  decode.loss_ce: 0.0321  decode.acc_seg: 75.2899  aux.loss_ce: 0.0133  aux.acc_seg: 75.1740
        2023/06/13 14:05:53 - mmengine - INFO - Iter(train) [1800/2000]  lr: 9.5983e-03  eta: 0:01:57  time: 0.5746  data_time: 0.0125  memory: 3979  loss: 0.0395  decode.loss_ce: 0.0277  decode.acc_seg: 85.8154  aux.loss_ce: 0.0119  aux.acc_seg: 80.2124
        2023/06/13 14:06:51 - mmengine - INFO - Iter(train) [1900/2000]  lr: 9.5760e-03  eta: 0:00:58  time: 0.5950  data_time: 0.0233  memory: 3979  loss: 0.0366  decode.loss_ce: 0.0258  decode.acc_seg: 87.4329  aux.loss_ce: 0.0108  aux.acc_seg: 85.7239
        2023/06/13 14:07:49 - mmengine - INFO - Exp name: pspnet-WatermelonDataset_20230613_20230613_134700
        2023/06/13 14:07:49 - mmengine - INFO - Iter(train) [2000/2000]  lr: 9.5536e-03  eta: 0:00:00  time: 0.5717  data_time: 0.0123  memory: 3979  loss: 0.0356  decode.loss_ce: 0.0247  decode.acc_seg: 83.7280  aux.loss_ce: 0.0108  aux.acc_seg: 78.4607
        2023/06/13 14:07:49 - mmengine - INFO - Saving checkpoint at 2000 iterations
        2023/06/13 14:08:00 - mmengine - INFO - per class results:
        ```

    - **测试日志**
        ```shell
        2023/06/13 14:13:46 - mmengine - WARNING - The prefix is not set in metric class IoUMetric.
        2023/06/13 14:13:47 - mmengine - INFO - Load checkpoint from work_dirs/WatermelonDataset/best_aAcc_iter_1600.pth
        2023/06/13 14:14:46 - mmengine - INFO - per class results:
        2023/06/13 14:14:46 - mmengine - INFO - 
        +------------+-------+-------+
        |   Class    |  IoU  |  Acc  |
        +------------+-------+-------+
        |     /      |  83.9 |  97.4 |
        |    red     | 86.83 | 91.81 |
        | seed-black | 16.89 | 18.17 |
        |   green    | 60.21 | 63.15 |
        | seed-white | 59.99 | 84.05 |
        |   white    |  0.14 |  0.14 |
        +------------+-------+-------+
        2023/06/13 14:14:46 - mmengine - INFO - Iter(test) [11/11]    aAcc: 87.9000  mIoU: 51.3200  mAcc: 59.1200  data_time: 0.0357  time: 5.3466
        ```

    - **测试图片**
        ![test](./test.png)

    - **预测结果：由于这张图片还采集到了整个西瓜，忽略其中部分即可**
        ![pred](./pred.jpg)