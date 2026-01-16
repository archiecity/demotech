# conda管理总结



先去anaconda官网里下载miniconda，下载出来的文件就是miniconda，记好路径，这里以D:\aaapp\miniconda这个路径为例

配置三个环境变量

```
D:\aaapp\miniconda
D:\aaapp\miniconda\Scripts
D:\aaapp\miniconda\Library\bin
```

**配置环境变量后一定要点确定，并且在IDE也需要关闭再重启!!!!!!!**

之后在IDE的右下角把那个菜单点出来，点击解释器设置，在右上角点添加新的解释器，跳出弹窗让你选择路径的时候找这个↓路径就可以成功添加了

```
D:\aaapp\miniconda\Scripts\conda.exe
```

之后需要什么包也可以去anaconda官网去搜，搜也是给你一个conda命令让你在命令行下载

**# test_env 是环境名**

## 检查conda 下的已有的环境 

```
conda env list
```

## 创建conda下的虚拟环境()

```
conda create -n test_env #直接创建
conda create -n test_env python=3.10 # 创建环境的时候直接指定（建议优先指定python版本）
```

## 激活虚拟环境

```
conda activate test_env # 成功后命令行最前面会出现环境名
```

## 删除环境,退出环境

```
conda deactivate (退出环境)
conda env remove -n pytorch_env(删除pytorch_env环境)
```

## conda 下载或修改已有环境的python版本（任何库都可以）

```
conda install python=3.x
这种方法只能下载轻型的库，若是大型的库，需要前往官网搜索，官网会给你完整命令的，复制进终端执行即可
 https://anaconda.org
```

## 检查python版本（任何库都可以）

```
python --version
```

## 查看已安装的包

```
conda list		  （查看本环境下所有的包）
conda list numpy  (检查numpy包的信息)
```

## pytorch下载

```python
 conda install pytorch torchvision torchaudio pytorch-cuda=12.1 -c pytorch -c nvidia  （最好不要只conda pytorch ,还需要一些辅助包来启动GPU加速
```







# 其他问题

## pip 与conda的混用问题

最好不要pip 与conda混用（除非实在没办法解决）

先用conda list 检查一下，看看channel信息是否显示是pypi，如果是，就pip uninstall numpy删除 再用conda下载，因为来自pypi的优先级最高

## 误报错问题

pycharm有时候无法检测到你新安装的库，这是正常现象，可以使用命令行

```
python name.py
```

进行运行