## mac m1下的python环境安装2023.8



```shell
# arm上使用需要安装Miniforge
# 其他试过了，不幸的我，折腾了几个钟
brew install miniforge
# 创建环境
conda create --name tf38
# conda初始化，我的是zsh
conda init zsh
# 切换环境 
conda activate tf38
# 安装python环境
conda install -y python==3.8.6
# 安装一些必备
conda install -y pandas matplotlib scikit-learn jupyterlab
# conda 一些命令
conda -V
# conda创建指定版本的python环境
conda create --name tf38 python=3.11
# 列出当前所有环境
conda info --envs
con env list
# 进入环境
conda activate tf38
# 退出环境
deactivate
# 复制环境
conda create --name new-env --clone old-env
# 删除环境
conda remove --name tf38 --all
# 分享环境
conda env export > enviroment.yml
# 复制分享的环境
conda env create -f environment.yml
# 包管理
# 查看所有
conde list

# pycharm添加地址
/opt/homebrew/Caskroom/miniforge/base/envs/tf38

# jupter启动
jupyter lab
```

