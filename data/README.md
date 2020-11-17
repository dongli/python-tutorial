# 配置Python软件包源

## Anaconda源

修改`~/.condarc`文件
```
channels:
  - defaults
show_channel_urls: true
channel_alias: https://mirrors.tuna.tsinghua.edu.cn/anaconda
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/pro
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
```
然后运行
```
conda clean -i
```

## Pip源

修改或创建`~/.pip/pip.conf`或`~/.config/pip.conf`文件
```
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
[install]
trusted-host=mirrors.aliyun.com
```

# FAQ

## 在Ubuntu上安装Cartopy

首先，安装依赖包：
```
# apt install libproj-dev libgeos-dev proj-bin
```
*注意*：必须安装`proj-bin`，否则会遇到如下错误：
```
Collecting cartopy
  Using cached Cartopy-0.18.0.tar.gz (14.4 MB)
    ERROR: Command errored out with exit status 1:
     command: /opt/conda/bin/python3.8 -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'/tmp/pip-install-mpnp7stg/cartopy/setup.py'"'"'; __file__='"'"'/tmp/pip-install-mpnp7stg/cartopy/setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' egg_info --egg-base /tmp/pip-pip-egg-info-9spqq6xg
         cwd: /tmp/pip-install-mpnp7stg/cartopy/
    Complete output (1 lines):
    Proj 4.9.0 must be installed.
```