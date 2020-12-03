本项目是学习入门Pytorch的造轮子，如果没预先下好数据集，文件中把download改为True，会放在文件夹./data下
# Learn-Pytorch
1. pytorch-tutorial，参考：https://github.com/yunjey/pytorch-tutorial 
    - pytorch_basic.ipynb：
    包括autograd的学习，tensor和numpy之间的转化，torchvision下载数据集，
    DataLoader新建loader对象，下载模型，fine-tune模型，保存模型
    - linear_regression.ipynb：
    构造一组数据（15个点），通过简单的线性回归，对点进行线性拟合，保存模型
    - linear_classification.ipynb：
    数据集为MNIST，放于./data目录下，用线性模型分类，83%测试结果
    - feedforward_neural_network.ipynb：
    数据集为MNIST，通过神经网络（FC-FC的两层网络）进行分类，97.91%测试结果
    - convolutional_neural_network.ipynb：
    数据集为MNIST，通过CNN（CONV-CONV-FC）进行分类，99.06%测试结果
    - deep_residual_network.ipynb：
    数据集为CIFAR10，通过类似ResNet18的网络（3层：2,2,2）进行分类，迭代约5个epochs，68.24%测试结果
2. 用PyTorch从零创建 CIFAR-1D 的图像分类器神经网络，参考：https://cloud.tencent.com/developer/article/1383124
    - VGG_network.ipynb：
    数据集为CIFAR10，通过VGG-16进行分类，迭代约40个epochs，83.86%测试结果  
3. pytorch实现ResNet（包括18、34、50、101、152），感觉比tutorial中代码写的好一些，参考：https://blog.csdn.net/winycg/article/details/86709991
    - ResNet.py：
    定义了两种block，实现ResNet（包括18、34、50、101、152）  
    - ResNet_train.ipynb：
    数据集为CIFAR10，通过ResNet18（4层：2,2,2,2）进行分类，迭代约6个epochs，75.21%测试结果  
    尺寸缩小发生在每个layer的第一个block中的3x3Conv，下采样发生在除了第一个layer的每个layer的第一个block，
    整个训练过程下来，(3x32x32)经过3次(layer1,2,3)的Conv和一次Pool(4)变为(512x1x1)。
    与原作不同的根本在于，原作是224x224的输入，因而每个layer都有尺度缩小，每个layer的第一个block都存在下采样。
4. 结构图
    - ResNet50.png/ResNet50_.png: ResNet50的结构图，在看维度有用
5. 其他工具
    - json2vocxml.py: 将PCB_DATASET的json标准文件分拆成VOC格式下的单个xml标注文件