# MNIST_TRAIN
MNIST训练过程以及利用结果识别数字图片
环境：Ubuntu16.04 64位;
Python3;
TensorFlow V1.5.0

关于mnist.py:
tensorflow提供了一套可视化的工具，就是tensorboard，它可以帮你绘制计算图，还可以记录训练过程中参数的变化情况并绘制成变化图，其使用会用到tf.summary.xxx这些API。首先在构建计算图的时候一个变量一个变量搜集，构建完后将这些变量合并然后在训练过程中写入到event文件中。(本文代码会创建mnistEven文件夹)
训练完成后 执行$ tensorboard --logdir="这里写mnistEven的路径"，然后再通过浏览器输入地址：”localhost:6006”，来看tensorboard。
效果如下：
![22](https://user-images.githubusercontent.com/29486192/35478441-98e7ae7a-0418-11e8-99fd-eee9ab1551a5.png)

关于保存模型，保存模型其实是保存了模型中的参数，主要是权重W和偏置b。保存到指定的目录下的是二进制文件，我们可以重构了网络之后，直接从这些文件中restore参数，就可以直接使用。另外要注意saver.save的参数

执行完本代码就可以在你指定的文件夹下生成训练模板

如下为识别结果
![识别结果](https://user-images.githubusercontent.com/29486192/35478413-dbf2163e-0417-11e8-9c85-0e64c9b62e96.png);
