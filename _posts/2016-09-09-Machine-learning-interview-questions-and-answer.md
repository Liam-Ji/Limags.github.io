---
title: 机器学习面试题
layout: post
tags:
  - Machine Learning
  - Interview
---
### 1. 什么是机器学习？

机器学习是计算机科学的的一个分支，是能够利用已有的数据和经验自动学习和提高的系统编程。
例如，机器人内部程序能够基于传感器数据处理一些任务，它能够从数据中自动学习规律。

### 2. 数据挖掘和机器学习有什么区别？

机器学习指研究、设计、开发不需要明确编程的，能够赋予计算机学习能力的算法。数据挖掘一般
指从大量数据中搜索隐藏信息和模式的过程，在这过程中可能会用到机器学习算法。

### 3. 什么是过拟合？

在机器学习过程中，当统计模型描述了随机错误或者噪声而不是数据本身的模式，就出现了过拟合。
通常，模型复杂度过高会观察到过拟合，因为相对于训练数据类型来说模型参数太多了。

### 4. 为什么会发生过拟合？

因为训练模型的表现并不能用来评判整个模型的优劣，整个模型还包括预测模型的表现。

### 5. 如何避免过拟合？

使用足够多的数据可以避免过拟合，通常训练用的数据量太小就会发生过拟合。
在比较小的数据集上学习模型可以使用交叉验证。将数据分为测试集和训练集两部分，测试集用于
测试，训练集用于产生模型。这种情况下，模型通常在已知数据上产生，在未知数据上测试。交叉
验证的理念是在训练阶段定义数据集来测试。

### 6. 什么是归纳式学习？

归纳式学习即通过例子学习，系统试图通过观察到的实例推导出一般性的法则。

### 7. 几个相对比较流行的机器学习算法

- 决策树
- 神经网络（反向传播）
- 概率图网络
- 最近邻
- 支持向量机

### 8. 机器学习中的算法有哪些类型？

- 监督学习
- 非监督学习
- 半监督学习
- 强化学习
- 遗传算法

### 9. 机器学习构建假设空间或模型的三部？

- 建立模型
- 测试模型
- 应用模型

### 10. 监督式学习的标准方法是什么？

监督式学习的标准方法是将样本集分成测试集和训练集。

### 11. 训练集和测试集分别指什么？

在各种类似机器学习的信息科学领域中，用来搜索潜在的数据关系的数据集称为训练集，训练集是
用来学习的样例，测试集用来评估学习出来的关系的准确率。

### 12. 列出机器学习中互相不同的方法

- 概念/分类学习
- 符号/统计学习
- 归纳/分析学习

### 13. 不是机器学习的例子？

- 人工智能
- 基于规则的推论

### 14. 解释非监督学习的作用

- 搜索数据中的簇
- 寻找数据的低维表示方式
- 搜索数据的兴趣方向
- 兴趣坐标和相关性
- 搜索异常/数据清洗

### 15. 解释监督学习的作用

- 分类
- 语言识别
- 回归
- 时间序列预测
- 文本标注

### 16. 解释机器学习中的算法独立

机器学习中的算法独立指其中的数学基础独立于任何特定的分类器或学习算法。

### 17. 机器学习和人工学习的区别？

机器学习根据经验数据的表现设计和开发算法。人工智能在此基础上还包括知识表现、自然语言
处理、规划、机器人等方面。

### 18. 机器学习中的分类器？

是机器学习中输入离散向量或连续特征值输出单个离散值（类别）的系统。

### 19. 朴素贝叶斯的优点？

朴素贝叶斯分类器比判别模型（logistic回归）收敛更快，所以需要的数据量更少。但不能学习
特征之间的关系。

### 20. 模式识别应用领域

- 计算机视觉
- 语音识别
- 数据挖掘
- 统计
- 数据检索
- 生物信息学

### 21. 什么是基因（遗传）编程？

基因编程是机器学习算法的一种，该模型基于对结果集合的测试和选择。

### 22. 什么是归纳逻辑编程(Inductive logic programming (ILP))？

机器学习的子类别，使用逻辑编程展现背景经验和例子。

### 23. 什么是选择模型？

即在不同用来描述相同数据集的数学模型中选择模型的过程。应用于统计学习、机器学习和数据挖掘
领域。

### 24. 监督式学习的两种校准方法？

- Platt Calibration
- Isotonic Regression

这两种方法都用于二元分类。

### 25. 常用于防止过拟合的方法？

当数据量足够大时使用保序回归(Isotonic Regression)来防止过拟合。

### 26. 基于规则的学习和决策树中的启发法有什么区别？

决策树中启发法评估离散数据集的平均数，而基于规则学习中的启发法只评估符合候选规则的数据集。

### 27. 什么是感知机？

一种用于监督式学习方法的算法，将输入变成可能的非二进制输出。

### 28. 解释贝叶斯逻辑编程的两个部分？

第一部分时逻辑，包括一个贝叶斯规则的集合，用来检测规定区域的定性结构；第二部分是定量部分，
用来编码规定区域的量化信息。

### 29. 什么是贝叶斯网络(BN)？

贝叶斯网络表述变量之间关系的图模型

### 30. 为什么基于实例的学习算法又被叫做懒惰学习算法？

因为基于实例的学习算法将归纳和泛化处理推迟到分类任务执行时。

### 31. 支持向量机能处理哪两种分类方法？

- 集成二元分类
- 改进版适应多元分类

### 32. 集成编程(ensemble learning)？

为解决特定任务，集成分类器和专家模型的过程称为集成编程。

### 33. 为什么使用集成编程？

提高分类、预测和回归等模型的准确性。

### 34. 什么时候使用集成编程？

构建更加精确的分类器部件并且各部件之间相互独立。

### 35. 集成编程范例？

集成编程的两个范例：
- 串行集成编程
- 并行集成编程

### 36. 集成编程的一般法则，什么是bagging和boosting？

集成编程的一般法则是，结合给顶算法的多个模型来提神稳定性。bagging集合多个分类器来提升
预测或分类的稳定性的方法。boosting是串行集成模型，用来减少集成模型的偏差。

### 37. 集成模型中的偏差-方差分解？

算法的预测错误可分解为偏差和方差两部分。偏差表示算法产生的分类器均值和目标函数的距离。
方差表示算法在不同测试集上的预测波动。

### 38. 集成算法中的增强学习？

增强学习是该算法从新数据中学习的能力，新数据区别于用来构建算法模型的旧数据。

### 39. 什么是PC A, KPCA, 和 ICA？

PCA (Principal Components Analysis), KPCA ( Kernel based Principal Component Analysis)
和 ICA ( Independent Component Analysis) 是维度约减中重要的特征抽取技术。

### 40. 什么是维度约减？

在机器学习和统计学中，维度约减是减少相关随机变量数目的过程，分为特征选择和特征抽取。

### 41. 什么是支持向量机？

用于分类和回归分析的监督学习算法。

### 42. 相关评估技术的组成？

相关评估技术的重要组成部分是：
- 数据获取
- 背景信息获取
- 交叉验证技术
- 问题类型
- 评估标准
- 重要测试

### 44. 序列预测问题在机器人和信息处理领域分别是哪些？

- 模仿学习
- 结构化预测
- 基于模型的强化学习

### 45. 什么是批统计学习？

统计学习允许学习函数或则预测器从观察到的数据学习信息以便用于将来的数据预测。这种技术
保证了已经学习过的预测器对未来位置数据预测的表现。

### 46. 什么是PCA学习？

PAC (Probably Approximately Correct)是用来分析学习算法和和统计算法效率的学习框架。

### 47. 序列学习的分类？

- 序列预测
- 序列产生
- 序列识别
- 序列决策

### 48. 什么是序列学习？

一种以逻辑方式连续教和学的方法。

### 49. 机器学习的两种技术？

- 基因编程
- 归纳学习

### 50. 举例说明生活中机器学习的流行应用

大型商业网站使用的推介引擎。