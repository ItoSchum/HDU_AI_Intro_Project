# HDU_Course_AI_Intro_Assignment

- 训练数据集：<https://archive.ics.uci.edu/ml/machine-learning-databases/breast-cancer-wisconsin/breast-cancer-wisconsin.data>
  

## LogisticRegression (逻辑斯蒂回归 分类器)

```
from sklearn.linear_model import LogisticRegression

LR = LogisticRegression()
LR.fit(X_train, y_train)
LR.predict(X_test)
LR.score(X_test,y_test)
```
Out: 0.9883040935672515

- **结论：** 通过比较，逻辑斯蒂模型比随机梯度下降模型在测试集上表现有更高的准确性，因为逻辑斯蒂采用解析的方式精确计算模型参数，而随机梯度下降采用估计值
- **特点分析：** 逻辑斯蒂对参数的计算采用精确解析的方法，计算时间长但是模型性能高，随机梯度下降采用随机梯度上升算法估计模型参数，计算时间短但产出的模型性能略低，一般而言，对于训练数据规模在10万量级以上的数据，考虑到时间的耗用，推荐使用随机梯度算法


## SGDClassifier (梯度下降 分类器)

```
from sklearn.linear_model import SGDClassifier
```
```
SGD = SGDClassifier(loss='hinge', penalty='l2', alpha=0.001, l1_ratio=0.15, fit_intercept=True, max_iter=None, tol=None, shuffle=True, verbose=0, epsilon=0.1, n_jobs=1, random_state=None, learning_rate='optimal', eta0=0.0, power_t=0.5, class_weight=None, warm_start=False, average=False, n_iter=None)
SGD.fit(X_train,y_train)
SGD.predict(X_test)
SGD.score(X_test,y_test)
```
Out: 0.9824561403508771

## LinearRegression (线性回归 分类器)
```
from sklearn.linear_model import LinearRegression
```
```
LR2 = LinearRegression(fit_intercept=True, normalize=False, copy_X=True, n_jobs=1)
LR2.fit(X_train,y_train)
LR2.predict(X_test)
LR2.score(X_test,y_test)
```
Out: 0.8739645029687063


## KNeighborsClassifier (k近邻 分类器)
```
from sklearn.neighbors import KNeighborsClassifier
```
```
KNN = KNeighborsClassifier(n_neighbors=5, weights='uniform', algorithm='auto', leaf_size=30, p=2, metric='minkowski', metric_params=None, n_jobs=1, **kwargs)
KNN.fit(X_train,y_train)
KNN.predict(X_test)
KNN.score(X_test,y_test)
```
Out: 0.9883040935672515

## GaussianNB (朴素贝叶斯 分类器)
```
from sklearn.naive_bayes import GaussianNB
```
```
GNB = GaussianNB(priors=None)
GNB.fit(X_train,y_train)
GNB.predict(X_test)
GNB.score(X_test,y_test)
```
Out: 0.9766081871345029