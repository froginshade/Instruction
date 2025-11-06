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

## 安装包
conda install -n *venv_name* *package_name*
## 查看包
conda list *package_name*
## 移除包
conda remove -n *venv_name* *package_name*
## 清理缓存
conda clean --all (--yes)

# pip
## 清理缓存
pip cache purge

