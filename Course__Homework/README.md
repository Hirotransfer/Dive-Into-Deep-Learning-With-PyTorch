# 刷分题（Fashion-mnist分类任务）
# Fashion-mnist分类任务

[经典的MNIST数据集](http://yann.lecun.com/exdb/mnist/)包含了大量的手写数字。十几年来，来自机器学习、机器视觉、人工智能、深度学习领域的研究员们把这个数据集作为衡量算法的基准之一。你会在很多的会议，期刊的论文中发现这个数据集的身影。实际上，MNIST数据集已经成为算法作者的必测的数据集之一。有人曾调侃道：*"如果一个算法在MNIST不work, 那么它就根本没法用；而如果它在MNIST上work, 它在其他数据上也可能不work！"*
 

`Fashion-MNIST`的目的是要成为MNIST数据集的一个直接替代品。作为算法作者，你不需要修改任何的代码，就可以直接使用这个数据集。`Fashion-MNIST`的图片大小，训练、测试样本数及类别数与经典MNIST**完全相同**。

这个数据集的样子大致如下（每个类别占三行）：

![](https://github.com/zalandoresearch/fashion-mnist/raw/master/doc/img/fashion-mnist-sprite.png)


## 类别标注

在Fashion-mnist数据集中，每个训练样本都按照以下类别进行了标注：

| 标注编号 | 描述 |
| --- | --- |
| 0 | T-shirt/top（T恤）|
| 1 | Trouser（裤子）|
| 2 | Pullover（套衫）|
| 3 | Dress（裙子）|
| 4 | Coat（外套）|
| 5 | Sandal（凉鞋）|
| 6 | Shirt（汗衫）|
| 7 | Sneaker（运动鞋）|
| 8 | Bag（包）|
| 9 | Ankle boot（踝靴）|


## 任务描述


`Fashion-MNIST`是一个替代[MNIST手写数字集](http://yann.lecun.com/exdb/mnist/)的图像数据集。 它是由Zalando（一家德国的时尚科技公司）旗下的[研究部门](https://research.zalando.com/)提供。其涵盖了来自10种类别的共7万个不同商品的正面图片。Fashion-MNIST的大小、格式和训练集/测试集划分与原始的MNIST完全一致。60000/10000的训练测试数据划分，28x28的灰度图片。你可以直接用它来测试你的机器学习和深度学习算法性能，且**不需要**改动任何的代码。


本次任务需要针对`Fashion-MNIST`数据集，设计、搭建、训练机器学习模型，能够尽可能准确地分辨出测试数据地标签。


## 文档说明 


数据集文件分为训练集和测试集部分，对应文件如下：

- 训练数据：`train-images-idx3-ubyte.gz` 
- 训练标签：`train-labels-idx1-ubyte.gz`
- 测试数据：`t10k-images-idx3-ubyte.gz`

## 参考文献

[1] Fashion-MNIST: a Novel Image Dataset for Benchmarking Machine Learning Algorithms. Han Xiao, Kashif Rasul, Roland Vollgraf. arXiv:1708.07747

[2] https://github.com/zalandoresearch/fashion-mnist/

# 评估说明

## 评价指标

本次任务采用 [ACC（Accuracy)](https://baike.baidu.com/item/%E5%87%86%E7%A1%AE%E7%8E%87) 作为模型的评价标准。

## 在线评估

评估函数首先会验证选手提交的预测结果文件是否符合要求，主要验证了以下要求:

1. 提交的预测文件是否存在重复ID
2. 提交的预测文件ID是否与测试集文件ID不匹配

通过验证后的文件会用以ACC为测评指标的函数进行计算评估。


## 文件格式

由于测评脚本已经统一，为保证脚本的顺利运行，在进行测评时，要求选手提交的`预测文件`拥有规范的字段名和字段格式，预测文件具体要求如下：

| NO | 字段名称 | 数据类型 | 字段描述 |
| -------- | -------- | -------- | -------- |
| 1    | ID     | int    | ID序列     |
| 2    | Prediction   | int     | 预测结果（类别值）   |

正确格式的提交文件样例: `submission_random.csv`。

## 基准算法

本次任务采用不同的基准算法，获得模型的ACC如下：
- 随机基准算法ACC：0.09440
- 弱基准算法ACC：0.90452

在评估时，以弱基准算法的ACC作为达标线。

# 开放题（卷积神经网络开放题）

# 卷积神经网络开放题

## 问题一：
- 阅读提出上述两种网络（**LeNet和AlexNet**）的相关论文，试从数据集的**预处理**、**激活函数**的使用、**训练方法**的改进以及**模型结构**的变化等角度，从理论层面分析比较`LeNet与AlexNet的结构差异`，并尝试解释AlexNet为什么会具有对计算机视觉任务优越的处理性能。

- AlexNet对Fashion-MNIST数据集来说可能过于复杂，请尝试对**模型**进行**简化**来使训练更快，同时保证`分类准确率`（accuracy）不明显下降（不低于85%），并将**简化后的结构**、**节省的训练时间**以及**下降的准确率**等相关指标以`表格`的形式进行总结分析。

## 问题二：
- **LeNet与AlexNet**在`接近图像输入的卷积模块`中都引入了**较大尺寸的卷积核**，如$5\times 5$或者$7\times 7$的卷积窗口来捕捉更大范围的图像信息，试分析**VGG每个基础块**的固定设计是否会影响到**图像的粗粒度**信息提取，并且对比**不同结构模块输出的特征图**进行对比。
- 尝试将Fashion-MNIST中图像的`高和宽由224改为96`，试分析**VGG网络**的参数变化情况，并且对比模型训练时间、分类准确率（accuracy）等实验指标受到的影响，以表格的形式进行总结分析。

## 问题三：
- 对比**AlexNet、VGG和NiN、GoogLeNet**的`模型参数尺寸`，从理论的层面分析为什么后两个网络可以显著减小模型参数尺寸？
- GoogLeNet有数个后续版本，包括加入**批量归一化层 [7]**、对**Inception块做调整 [8]** 和**加入残差连接 [9]**，请尝试实现并运行它们，然后观察实验结果，以表格的形式进行总结分析。
