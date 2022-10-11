# Machine Learning（机器学习）

[TOC]

### 1.什么是机器学习

机器学习就是让机器具备找一个函式的能力。

### 2.Different types of Functions（机器学习的不同类型）

​	Regression：回归问题，要找的函式, 他的输出是一个数值

​	Classification: 分类问题，函式的输出,就是从设定好的选项裡面,选择一个当作输出

​	Structured Learning: 结构学习，机器產生有结构的东西的问题——学会创造（输出一个有结构的内容，比如一张图片，一段话）

### 3.机器学习步骤

##### 1.Function with unknown parameters(写出一个带有未知参数的函数)

​	（Ex. Linear Model y=wx+b，这里y是我们准备要预测的东西，即是一个model，w、b为待训练的参数）

![img](https://diamond-mule-bee.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Ffaba6ee8-754f-4783-9cca-ad8602b14d25%2FUntitled.png?table=block&id=05bee57f-e18e-4c3e-97f3-a9ec8ffaf822&spaceId=effd33e2-527b-43dc-aef5-7b5ee7b83428&width=1720&userId=&cache=v2)

- 名词定义	

​	**Feature** （特征）: Function裡面我们已知的信息( X1 )

​	**Weight**（权重）：未知参数，跟feature直接相乘

 	**Bias**（偏差）：模型预测的值和真实值之间的距离的期望，代表算法的拟合能力 

##### 2.Define Loss from Training Data(确定评价标准，定义Loss函数)

Loss也是一个Function，即损失函数, 它的输入,是Model裡面的参数

- 代表我们这一组参数的好坏程度，L越大,代表一组参数越不好,L越小,代表现在这一组参数越好
- 计算方法：模型预测的值跟实际的值（Label） 之间的差距
  - MAE(mean absolute error) 
  - MSE(mean square error)
  - Cross-entropy:计算概率分布之间的差距

![img](https://diamond-mule-bee.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fb7eb0ae8-8edd-45c0-ad0b-6ad00f39eb3d%2FUntitled.png?table=block&id=95db3bfe-326c-4362-8344-8fde263889e0&spaceId=effd33e2-527b-43dc-aef5-7b5ee7b83428&width=1970&userId=&cache=v2)

##### 3.Optimization(此处优化的方法为梯度下降Gradient decent)

找到能让损失函数值最小的参数。





# Liner Model（线性模型）

根据周期性，修改模型⇒考虑**前7天，甚至更多天**的值

Model 的Bias：一个模型无法模拟/描述真实的情况

⇒解决方法：需要一个更复杂的、更有弹性的、有未知参数的function

### Piecewise Linear Curves（Sigmoid函数的意义）

##### 1.模型定义

定义：由多段锯齿状的线段所组成的线

⇒可以看作是一个常数,再加上一堆蓝色的 Function**（Hard Sigmoid)**

> **用一条曲线来近似描述这条蓝色的曲线:Sigmoid函数（S型的function）**
>
> 【事实上，sigmoid的个数就是神经网络中的一层的neuron节点数(使用几个sigmoid是**超参数**）】

$y=b+\sum_isigmoid(b_i+w_ix_i)$

![img](https://diamond-mule-bee.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fbda4083c-f713-4ea9-8f0e-4511e2f04228%2FUntitled.png?table=block&id=d957317a-1ed9-4458-8ee3-5bdd12bf30dc&spaceId=effd33e2-527b-43dc-aef5-7b5ee7b83428&width=1970&userId=&cache=v2)

**结论：**

1. 可以用 **Piecewise Linear** 的 Curves,去**逼近任何的连续的曲线**
2. 每一个 Piecewise Linear 的 Curves,都可以用**一大堆蓝色的 Function加上一个常量组合**起来得到
3. 只要有**足够的蓝色 Function** 把它加起来,就可以变成任何连续的曲线

