# Deep Learning Cheat Sheet

## conda换源

```shell
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```

```shell
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
```

## 安装PyTorch

```shell
conda install pytorch torchvision cudatoolkit=10.0
```

remember we should delete `-c pytorch` in order to install pytorch from https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch



