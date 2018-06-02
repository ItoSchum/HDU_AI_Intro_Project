# HDU_AI_Intro_Project

- 训练数据集：<https://archive.ics.uci.edu/ml/machine-learning-databases/breast-cancer-wisconsin/breast-cancer-wisconsin.data>
  
## 逻辑斯蒂回归分类器

- **结论：** 通过比较，逻辑斯蒂模型比随机梯度下降模型在测试集上表现有更高的准确性，因为逻辑斯蒂采用解析的方式精确计算模型参数，而随机梯度下降采用估计值
- **特点分析：** 逻辑斯蒂对参数的计算采用精确解析的方法，计算时间长但是模型性能高，随机梯度下降采用随机梯度上升算法估计模型参数，计算时间短但产出的模型性能略低，一般而言，对于训练数据规模在10万量级以上的数据，考虑到时间的耗用，推荐使用随机梯度算法
