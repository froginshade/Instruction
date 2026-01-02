# conda虚拟环境
## 创建环境
conda create -n *venv_name* python=*3.9*
## 激活环境
conda activate *venv_name*
## 退出环境
conda deactivate
## 删除环境
conda remove -n *venv_name* --all
## 查看环境
conda info --envs
## 设置channels (全局)
conda config --remove-key channels
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
conda config --set channel_priority flexible/strict

## 检查使用的channels
conda config --show channels
## 检查channels优先级
conda config --show channel_priority
## 安装包
conda install -n *venv_name* *package_name*
## 查看包
conda list *package_name*
## 升级包
conda update *package_name*
## 移除包
conda remove -n *venv_name* *package_name*
## 清理缓存
conda clean --all (--yes)
## 管理包清单
conda env export --no-builds > environment.yml


# pip
## 设置源
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
## 更新pip
pip install pip -U
## 查看包
pip list/show *package_name*
## 升级包
pip install -U *package_name*
## 清理缓存
pip cache purge
