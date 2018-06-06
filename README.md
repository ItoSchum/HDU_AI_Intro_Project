# HDU Course: AI Intro - Assignment

- 训练数据集：[Breast Cancer Wisconsin (Diagnostic) Data Set] (https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29)

## Data Analysis

- **RangeIndex:** 569 entries, 0 to 568
- **Data Columns:** total 32 columns
- **Data Types:** float64(30), int64(1), object(1)
- **Memory Usage:** 142.3+ KB

- **Attribute Info：**
	1. 身份证号码
	- 诊断（M =恶性，B =良性）
	- 3-32为每个细胞核计算十个实值特征：
		- a）半径（从中心到周边点的距离的平均值）
		- b）纹理（灰度值的标准偏差）
		- c）周界
		- d）区域
		- e）光滑度（半径长度的局部变化）
		- f）紧凑性（周长^ 2 /面积 - 1.0）
		- g）凹度（轮廓凹部的严重程度）
		- h）凹点（轮廓的凹入部分的数量）
		- i）对称
		- j）分形维数（“海岸线近似” - 1）
		
		- 对每个数据分别求平均值，标准误差，“最差”或最大，产生30个特征。
		- 所有功能值都用四位有效数字重新编码。

## Data Visualization
- **相似相关性热力图**

- **加入分类的相关性热力图**
	- *New Correlation Features:*
		- 32 to 16 dimension
		- concavity_mean, concave points_mean, concave points_worst
		- compactness_mean, compactness_worst, concavity_worst
		- perimeter_mean, radius_mean, area_mean, perimeter_worst, radius_worst, area_worst
		- area_se, radius_se, perimeter_se
		- texture_mean, texture_worst
		- texture_se, smoothness_se, symmetry_se
		- fractal_dimesion_worst
		- smoothness_mean
		- smoothness_worst
		- symmetry_mean
		- symmetry_worst
		- concave points_se
		- compactness_se
		- concavity_se
		- fractal_dimession_mean
		- fractal_dimession_se

## Classification

Diagnosis    | Amount
------------ | -------------
B            | 268
M            | 158

### 32 features

- **Logistic Regression**
	- *Original*
	
	Item        | Precision | Recall   | f1-Score  | Support
	------------|-----------|----------|-----------|---------
	B           | 0.94624   | 0.98876  | 0.96703   |  89
	M           | 0.98000   | 0.90741  | 0.94231   |  54
	Avg / Total | 0.95899   | 0.95804  | 0.95770   |  143

	
	- *Depth Optimized* 
	>Accuracy is maximum at depth 100 and accuracy 0.979
	
	Item        | Precision | Recall   | f1-Score  | Support
	------------|-----------|----------|-----------|---------
	B           |   0.96739 | 1.00000  | 0.98343   |  89
	M           |   1.00000 | 0.94444  | 0.97143   |  54
	Avg / Total |   0.97971 | 0.97902  | 0.97890   |  143
 
- **kNN**
> Accuracy is max in Sample 10 and accuracy 0.9301

Item        | Precision | Recall   | f1-Score  | Support
------------|-----------|----------|-----------|---------
B           |   0.92473 |  0.96629 |  0.94505  |      89
M           |   0.94000 |  0.87037 |  0.90385  |      54
Avg / Total |   0.93050 |  0.93007 |  0.92949  |     143



- **Gaussian Naive Bayes**

Item        | Precision | Recall   | f1-Score  | Support
------------|-----------|----------|-----------|---------
B           |   0.92632 |  0.98876 |  0.95652  |      89
M           |   0.97917 |  0.87037 |  0.92157  |      54
Avg / Total |   0.94627 |  0.94406 |  0.94332  |     143

### 16 features

- *Drop Attributes:*
	- concave points_mean
	- concave points_worst 
	- compactness_worst
	- concavity_worst
	- radius_mean
	- area_mean
	- perimeter_worst
	- radius_worst
	- area_worst
	- radius_se 
	- perimeter_se
	- texture_worst 
	- smoothness_se 
	- symmetry_se

- **Logistic Regression**
> Accuracy is maximum at depth 1000 and accuracy 0.986

Item        | Precision | Recall   | f1-Score  | Support
------------|-----------|----------|-----------|---------
B           |   0.97802 |  1.00000 |  0.98889  |      89
M           |   1.00000 |  0.96296 |  0.98113  |      54
Avg / Total |   0.98632 |  0.98601 |  0.98596  |     143

- **kNN**
> Accuracy is max in Sample 5 and accuracy 0.9161

Item        | Precision | Recall   | f1-Score  | Support
------------|-----------|----------|-----------|---------
B           |   0.91398 |  0.95506 |  0.93407  |      89
M           |   0.92000 |  0.85185 |  0.88462  |      54
Avg / Total |   0.91625 |  0.91608 |  0.91539  |     143

- **Random Forest**

Item        | Precision | Recall   | f1-Score  | Support
------------|-----------|----------|-----------|---------
B           |   0.94624 |  0.98876 |  0.96703  |      89
M           |   0.98000 |  0.90741 |  0.94231  |      54
Avg / Total |   0.95899 |  0.95804 |  0.95770  |     143


## Dimension Reduction* (Unfinished)
- **PCA**
	- *Image:* K-means clustering on the digits dataset (PCA-reduced data)
