---
title: DeepLearning Note
tags: Deeplearning,Digits,Caffe,Ubuntu
grammar_cjkRuby: true
---

[toc]

# Digits学习
## 安装
### Ubuntu 安装
1. 有无GPU都可以安装Digits，在纯Ubt下可以识别GPU（如果有的话）。Ubt下如何安装显卡驱动详见LinuxNote。  
2. Digits的安装分为包安装和编译安装，这里采用包安装方式，比较简单
3. 第一步，安装依赖包
``` stylus
sudo apt-get install --no-install-recommends git graphviz gunicorn python-dev python-flask python-flaskext.wtf python-gevent python-h5py python-numpy python-pil python-protobuf python-scipy
```
4. 第二部，安装Cuda包和学习包（重要，否则无法安装digits）

``` stylus
# 获取CUDA包
CUDA_REPO_PKG=cuda-repo-ubuntu1404_7.5-18_amd64.deb
wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1404/x86_64/${CUDA_REPO_PKG} -O /tmp/${CUDA_REPO_PKG}
sudo dpkg -i /tmp/${CUDA_REPO_PKG}
rm -f /tmp/${CUDA_REPO_PKG}

# 获取学习包
ML_REPO_PKG=nvidia-machine-learning-repo-ubuntu1404_4.0-2_amd64.deb
wget http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1404/x86_64/${ML_REPO_PKG} -O /tmp/${ML_REPO_PKG}
sudo dpkg -i /tmp/${ML_REPO_PKG}
rm -f /tmp/${ML_REPO_PKG}

# 更新
sudo apt-get update
```
5. 第三部，安装Digits(这里会自动安装好Caffe等必要的库)

``` stylus
sudo apt-get install digits
```
6. 打开http://localhost:5000
7. 更多方式参考资源
# 相关资源
[官方安装Digits4.0](https://github.com/NVIDIA/DIGITS/blob/digits-4.0/docs/UbuntuInstall.md)
[Build方式安装Digits4.0](https://github.com/NVIDIA/DIGITS/blob/digits-4.0/docs/BuildDigits.md)
[Digits官方文档列表](https://github.com/NVIDIA/DIGITS/tree/master/docs)