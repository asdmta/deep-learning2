U-net 网络进行语义分割训练

环境配置：
1  Python3.6以上
2  Pytorch1.10
3  linux（Ubuntu或Centos）使用GPU进行训练

U-net文件夹内各个文件的作用：

1、src: 搭建U-Net模型
2、train_utils: 训练、验证以及多GPU训练相关模块
3、dataset.py: 自定义dataset用于读取DRIVE数据集(视网膜血管分割)
4、train.py: 以单GPU为例进行训练
5、train_multi.py: 针对使用多GPU的用户使用
6、predict.py: 使用训练好的权重进行预测测试
7、compute_mean_std.py: 统计数据集各通道的均值和标准差


DRIVE数据集下载地址:
https://pan.baidu.com/s/15owfbPtCOnIIPWW_-6WhQA  提取码：gt22



注意：
1、确保提前准备好数据集
2、train.py是进行单GPU训练的文件
3、torchrun --nproc_per_node=n train_multi.py是进行多GPU训练的文件，其中”n“是使用GPU的个数
4、如果想指定使用哪些GPU设备可在指令前加上CUDA_VISIBLE_DEVICES=n1,n2。n1，n2指的是第几个GPU的索引，从0开始，例如 0指的就是第一块

