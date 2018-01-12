---

layout:     post

title:      "Tensorflow in Ubuntu_16.04"

subtitle:   " 安装教程 "

date:       2018-01-12 20:42:00

author:     "Zz"

header-img: "img/default-bg.jpeg"

catalog: false

tags:

    - tensorflow
    

---




完整步骤|

## 1. CUDA 8.0

下载地址
[https://developer.nvidia.com/cuda-downloads](https://developer.nvidia.com/cuda-downloads)

选择runfile安装类型

安装时，不安装驱动，只安装Toolkits和Samples

出现以下信息时
```
Missing recommended library: libGLU.so 
Missing recommended library: libX11.so 
Missing recommended library: libXi.so 
Missing recommended library: libXmu.so
```
命令行运行以下代码并重新安装CUDA
`sudo apt-get install freeglut3-dev build-essential libx11-dev libxmu-dev libxi-dev libgl1-mesa-glx libglu1-mesa libglu1-mesa-dev `



## 2. cuDNN6.0

下载地址
[https://developer.nvidia.com/cudnn]( https://developer.nvidia.com/cudnn)

解压并运行以下命令
```
sudo cp cuda/include/cudnn.h /usr/local/cuda-8.0/include
sudo cp cuda/lib64/libcudnn* /usr/local/cuda-8.0/lib64
sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda-8.0/lib64/libcudnn*
```

## 3. 配置环境

```
sudo gedit ~/.bashrc
```
在末尾添加
```
export LD_LIBRARY_PATH=”$LD_LIBRARY_PATH:/usr/local/cuda/lib64:/usr/local/cuda/extras/CUPTI/lib64”

export CUDA_HOME=/usr/local/cuda

exportPATH="$CUDA_HOME/bin:$PATH"
```
保存并运行
```
source ~/.bashrc
```


## 4. Tensorflow

官方教程
[https://www.tensorflow.org/install/install_linux](https://www.tensorflow.org/install/install_linux)

**虚拟环境安装（推荐）**

1. 安装pip和虚拟环境依据python版本运行以下其中一条命令:
```
$ sudo apt-get install python-pip python-dev python-virtualenv # for Python 2.7
$ sudo apt-get install python3-pip python3-dev python-virtualenv # for Python 3.n
```

2. 运行以下命令创建虚拟环境
```
$ virtualenv --system-site-packages 目标文件夹 # for Python 2.7
$ virtualenv --system-site-packages -p python3 目标文件夹 # for Python 3.n
```

3. 激活虚拟环境
```
$ source ~/tensorflow/bin/activate # bash, sh, ksh, or zsh
$ source ~/tensorflow/bin/activate.csh  # csh or tcsh
```
会看到命令行变为以下形式
```
(tensorflow)$
```

4. 如果pip版本为8.1以上，运行
```
(tensorflow)$ easy_install -U pip
```

5. 选择合适的命令行安装
```
(tensorflow)$ pip install --upgrade tensorflow      # for Python 2.7
(tensorflow)$ pip3 install --upgrade tensorflow     # for Python 3.n
(tensorflow)$ pip install --upgrade tensorflow-gpu  # for Python 2.7 and GPU
(tensorflow)$ pip3 install --upgrade tensorflow-gpu # for Python 3.n and GPU
```

6. 每次使用Tensorflow的时候都要激活虚拟环境
```
$ source ~/tensorflow/bin/activate      # bash, sh, ksh, or zsh
$ source ~/tensorflow/bin/activate.csh  # csh or tcsh
```
不使用Tensorflow时，运行
```
(tensorflow)$ deactivate 
```

7. 卸载Tensorflow
```
$ rm -r targetDirectory 
```

8. 测试
```
$ python
import tensorflow as tf
hello = tf.constant('Hello, TensorFlow!')
sess = tf.Session()
print(sess.run(hello))
```
如果安装成功，会出现如下结果
```
Hello, TensorFlow!
```

**Congratulations！** 
