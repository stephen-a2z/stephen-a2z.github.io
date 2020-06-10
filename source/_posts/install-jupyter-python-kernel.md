---
title: 安装好jupyterhub后， 该如何安装我们需要的 ipython kernel 呢
date: 2020-06-09 20:17:14
tags: 
  - jupyter
  - notebook
  - ipython
  - kernel
  - conda
categories:
  - jupyter
---
# 安装好jupyterhub后， 该如何安装我们需要的 ipython kernel 呢
## 首先检查一下我们的环境
```sh
which conda
```
如果用tljh 安装的jupyterhub， 应该显示如下
```
/opt/tljh/user/bin/conda
```
接着我们查看下conda 当前的信息
```sh
conda info
```
下面是我的conda 信息， 这个信息对我们很重要
```
active environment : None
            shell level : 0
       user config file : /root/.condarc
 populated config files : /root/.condarc
          conda version : 4.8.3
    conda-build version : not installed
         python version : 3.8.2.final.0
       virtual packages : __glibc=2.27
       base environment : /opt/conda  (writable)
           channel URLs : https://conda.anaconda.org/conda-forge/linux-64
                          https://conda.anaconda.org/conda-forge/noarch
                          https://repo.anaconda.com/pkgs/main/linux-64
                          https://repo.anaconda.com/pkgs/main/noarch
                          https://repo.anaconda.com/pkgs/r/linux-64
                          https://repo.anaconda.com/pkgs/r/noarch
          package cache : /opt/conda/pkgs
                          /root/.conda/pkgs
       envs directories : /opt/conda/envs
                          /root/.conda/envs
               platform : linux-64
             user-agent : conda/4.8.3 requests/2.23.0 CPython/3.8.2 Linux/4.15.0-101-generic ubuntu/18.04.4 glibc/2.27
                UID:GID : 0:0
             netrc file : None
           offline mode : False
```

从上面的信息， 我们可以得到这些信息
- active environment : None # 代表当前是默认环境
- user config file : /root/.condarc  # config 文件的路径
- package cache :  # 安装包所在的路径
- envs directories:  # 环境路径
- channel URLs： # channel 地址
等等

## 创建环境


例如创建一个名为 myenv 的环境， 并且python版本为3.7 sqlite位指定版本 
```
conda create -n myenv sqlite python=3.7
```


创建完成后，我们可以用如下命令检查
```
conda env list
```
显示
```
python                   /opt/conda/envs/python
myenv                   /opt/conda/envs/myenv
```

## 创建kernel
用myenv的环境创建一个名为 `mykernel` 的`kernel`， `kernel`保存在`/usr/local`
```
/opt/conda/envs/myenv/bin/python -m IPython kernel install --prefix=/usr/local --name mykernel
```
之后当我们note book 上选择kernel为mykernel时， python 的环境就是myenv 的环境了

可在notebook 中的ipython 中通过下面代码检测
```python
import sys
sys.executable
```
正常情况下显示
`/opt/conda/envs/myenv/bin/python`
代表我们的任务完成了✅

## 终端查看kernel
命令
```sh
jupyter kernelspec list
```
显示
```
Available kernels:
  python3       /opt/tljh/user/share/jupyter/kernels/python3
  python        /usr/local/share/jupyter/kernels/python
  python2       /usr/local/share/jupyter/kernels/python2
  mykernel        /usr/local/share/jupyter/kernels/mykernel
```


```python

```
