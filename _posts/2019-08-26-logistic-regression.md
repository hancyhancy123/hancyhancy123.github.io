---
layout: post
title:  "逻辑回归（Logistic Regression）"
date:   2019-08-26 11:34:05
categories: machine-learning
excerpt: Logistic Regression
---

logistic回归（Logistic Regression），不同于线性回归（Regression），是一种分类算法
$0<=h_\theta(x)<=1$	，y=1 或 y=0

###sigmod 函数/logistic 函数

   $$g(z)=\frac{1}{1+e^{-z}}$$

   $$h_\theta(x)=g(\theta^Tx)=\frac{1}{1+e^{-\theta^Tx}}$$

###假设陈述

   $$h_\theta(x)=estimated probability that y=1 on input x$$

   $$h_\theta(x)=P(y=1|x;\theta)$$

   $$y=\left\{\begin{matrix}
   1 & z\geq 0\\ 
   0 & z<0
   \end{matrix}\right.$$

###决策边界

   st. $z=\theta^Tx = 0$的边界

###代价函数

   $$J(\theta)=\frac{1}{m}\sum_{i=1}^{m}Cost(h_\theta(x^{(i)}),y^{(i)})$$

   $$Cost(h_\theta(x),y)=\left\{\begin{matrix}
   -log(h_\theta(x)) & if y=1\\ 
   -log(1-h_\theta(x)) & if y=0
   \end{matrix}\right.$$

   注：h_\theta(x)的形式注定Cost的选择不能线性回归里不一样，线性回归里的Cost Function（平方差和）的形式会使得最终J的结果震荡，不利于最终收敛，从而可能只能得到局部最优解。也就是说最终J的结果不满足凸优化（Convex Optimization）。

   <img src="{{site.baseurl}}/static/image/costFunc_1.png"  width="220px" height="200px"/><img src="{{site.baseurl}}/static/image/costFunc_2.png"  width="220px" height="200px" style="margin-left:100px"/>

   $$\begin{matrix}
   Cost(h_\theta(x),y)=0 & if & h_\theta(x)=y\\ 
   Cost(h_\theta(x),y)\rightarrow \infty & if & h_\theta(x)\rightarrow 1\\ 
   Cost(h_\theta(x),y)\rightarrow \infty & if & h_\theta(x)\rightarrow 0
   \end{matrix}$$

###简化版代价函数与梯度下降

   $$Cost(h_\theta(x),y)=-ylog(h_\theta(x))-(1-y)log(1-h_\theta(x))$$

   goal: $\underset{\theta}{min}J(\theta)$

   $$\theta_j=\theta_j-\\alpha \frac{\partial }{\partial \theta_j}J(\theta)$$

   $$=\theta_j-\alpha \sum_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})x_j^{(i)}$$

   线性回归中 $h_\theta(x)=\theta^Tx$，逻辑回归中$h_\theta(x)=\frac{1}{1+e^{-\theta^Tx}}$

   注：特征缩放有助于加快收敛速度。 

###高级优化

   "Conjugate gradient", "BFGS", and "L-BFGS" are more sophisticated, faster ways to
   optimize θ that can be used instead of gradient descent. 

###多元分类：一对多

   ![1566437357098]({{site.baseurl}}/static/image/multiregression.png)

   将n元分类问题划分为n个二元逻辑回归分类问题，最后取预测值最准的分类器。

### 参考资料
* [机器学习 吴恩达](https://study.163.com/course/courseMain.htm?courseId=1004570029&_trace_c_p_k2_=f1158da157aa45e29e9dc717d5be9260)

