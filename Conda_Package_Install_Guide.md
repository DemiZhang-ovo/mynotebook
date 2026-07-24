# Conda 完整下载/安装/更新/搜索/卸载包教程

## 一、基础安装命令格式

```bash
conda install 包名
```

带软件源（推荐，下载更快、包更全）：

```bash
conda install -c conda-forge 包名
```

`conda-forge` 是最大开源软件仓库，绝大多数Python库、科学计算包都在这里。

## 二、分步标准操作

1.  打开 **Anaconda Prompt**（别用系统CMD，否则找不到conda）

2. 激活你要装包的环境（你的项目环境）
   
   ```bash
   conda activate ycgs
   ```

3. 执行安装，以pyomo举例：
   
   ```bash
   conda install -c conda-forge pyomo
   ```

4. 弹出确认输入 `y` 回车，等待下载安装完成。

## 三、常用场景用法

### 1. 指定包版本安装

格式：`包名=版本号`

```bash
# 安装numpy 2.1.0版本
conda install -c conda-forge numpy=2.1.0
```

### 2. 一次性安装多个包

空格隔开包名即可

```bash
conda install -c conda-forge pyomo pandas matplotlib
```

### 3. 搜索包（不确定包名时）

```bash
conda search -c conda-forge 关键词
# 例：搜索和优化相关包
conda search -c conda-forge opt
```

### 4. 更新已安装的包

```bash
# 更新单个包
conda update 包名
# 更新当前环境所有包
conda update --all
```

### 5. 卸载不需要的包

```bash
conda remove 包名
```

## 四、找不到包怎么办？conda找不到就用pip

有些小众库没有conda版本，在激活环境后用pip安装：

```bash
# 已经激活环境下执行
pip install 包名
```

> 注意：pip安装的包只存在当前激活的conda环境里，切换环境需要重新装。

## 五、检查包是否安装成功

### 方式1：终端查看已安装包列表

```bash
conda list
```

### 方式2：Python代码验证

```python
import pyomo
print(pyomo.__version__)
```

无报错=安装成功。

## 六、常见问题解决

1. **conda不是内部命令**
   必须打开 Anaconda Prompt，不要用黑色CMD窗口；
2. **下载速度极慢**
   配置国内清华conda镜像源，大幅提速；
3. **VS Code导入库提示找不到**
   VS Code左下角解释器切换到目标conda环境；
4. **安装冲突报错**
   去掉 `-c conda-forge` 用官方源，或者新建干净虚拟环境安装。


