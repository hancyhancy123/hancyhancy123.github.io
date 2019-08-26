---
layout: post
title:  "逻辑回归（Logistic Regression）"
date:   2019-08-26 11:34:05
categories: machine-learning
excerpt: Logistic Regression
---

logistic回归（Logistic Regression），不同于线性回归（Regression），是一种分类算法
![CodeCogsEqn_1]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_1.png)
，y=1 或 y=0

### sigmod 函数/logistic 函数

![CodeCogsEqn_2]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_2.png)

![CodeCogsEqn_3]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_3.png)

### 假设陈述

![CodeCogsEqn_4]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_4.png)
<span>estimated probability that y=1 on input x</span>

![CodeCogsEqn_5]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_5.png)

![CodeCogsEqn_6]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_6.png)

### 决策边界

![CodeCogsEqn_7]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_7.png)

### 代价函数

![CodeCogsEqn_8]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_8.png)

![CodeCogsEqn_9]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_9.png)

   注：![CodeCogsEqn_0]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_0.png)的形式注定Cost的选择不能线性回归里不一样，线性回归里的Cost Function（平方差和）的形式会使得最终J的结果震荡，不利于最终收敛，从而可能只能得到局部最优解。也就是说最终J的结果不满足凸优化（Convex Optimization）。

   <img src="{{site.baseurl}}/static/image/costFunc_1.png"  width="220px" height="200px"/><img src="{{site.baseurl}}/static/image/costFunc_2.png"  width="220px" height="200px" style="margin-left:100px"/>

![CodeCogsEqn_10]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_10.png)

### 简化版代价函数与梯度下降

![CodeCogsEqn_11]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_11.png)

*goal:* ![CodeCogsEqn_12]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_12.png)

*gradient descent:*![CodeCogsEqn_13]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_13.png)

   线性回归中![CodeCogsEqn_14]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_14.png)，逻辑回归中![CodeCogsEqn_15]({{site.baseurl}}/static/image/codeEqn/CodeCogsEqn_15.png)。
   注：特征缩放有助于加快收敛速度。

### 高级优化

   "Conjugate gradient", "BFGS", and "L-BFGS" are more sophisticated, faster ways to
   optimize θ that can be used instead of gradient descent. 

### 多元分类：一对多

   ![1566437357098]({{site.baseurl}}/static/image/multiregression.png)

   将n元分类问题划分为n个二元逻辑回归分类问题，最后取预测值最准的分类器。

### 参考资料
* [机器学习 吴恩达](https://study.163.com/course/courseMain.htm?courseId=1004570029&_trace_c_p_k2_=f1158da157aa45e29e9dc717d5be9260)

