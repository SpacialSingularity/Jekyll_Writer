---
title: 达朗贝尔原理：从牛顿力学到拉格朗日力学
layout: post
categories: Physics
tags: 'Note, Mechanics, Ordinary'
---
## 前言

这篇文章同时有学习笔记和学习感想的性质：刚听完老师讲的分析力学课、看了课本的相应内容后感觉有些东西可以更加明朗地说出来，于是自己组织起来讲一遍。内容主要是从牛顿力学过渡到拉格朗日力学。

## 牛顿力学(Newton Mechanics)回顾

我们已经学过了牛顿力学，并用它来预测物体的运动。一般是首先选取牛顿第一定律成立的惯性参考系，然后对于每个物体利用牛顿第二定律列写微分方程（称为牛顿方程），其中力的形式可以由已知的其他规律给出。结合初始条件，就能确定物体的运动方程 ![TeX](https://math.jekyllwriter.com/?q=%5Cvec%20r%3D%5Cvec%20r(t)) 。

例如：铰接在固定支点的刚性轻杆连接着质点，对于质点可以列写包含加速度、弹力的微分方程。利用劲度系数很大（刚性很强）情形的胡克定律（Hooke's Law）对这个弹力线性进行近似地描述，可以消去弹力这一个未知量。基于刚性条件，通过“质点到支点恒等于杆长”给出的方程也可以消去一个未知量——如质点的极坐标表示中的坐标 r 。后者是一个更精简的近似，给出的约束方程仅仅是坐标的几何关系，称为几何约束，这时弹力被视为约束力。区别于主动力，在列牛顿方程时不需要给出约束力的具体表达式，而是通过约束方程消去之。

面对这类问题，我们往往需要对 N 个物体列写 3N 个微分方程并增补 k 个约束条件方程。有时，约束条件可以如上例那样直接用一个坐标表示另一个坐标，就预先消去了一个未知量，这通常是便利的。那么，在什么情况下，这个操作是可以完成的呢？进一步地，对于这类问题能否直接从牛顿方程出发推导出一种新的得到微分方程的方式、从而能够直接列写不包含约束力/约束条件的方程？

## 达朗贝尔原理(d'Alembert's Principle)

能否直接从牛顿方程出发推导出一种新的得到微分方程的方式、从而能够直接列写不包含约束力/约束条件的方程？
现在我们不考虑牛顿第二定律（力学规律）对物体的限制，认为物体可以在其他限制（这里指约束）允许的条件下任意运动。这样产生的位移称为虚位移，我们用变分 ![TeX](https://math.jekyllwriter.com/?q=%5Cdelta%5Cvec%20r) 表示它。变分运算和微分运算规律相似，它的数学意义也可以一定程度被微分体现，从而也不妨直观地理解为微分 ![TeX](https://math.jekyllwriter.com/?q=d%5Cvec%20r) 。

对于某个质点系中的某个质点，由牛顿第二定律有

![TeX](https://math.jekyllwriter.com/?q=%5Cunderbrace%7B%5Coverset%7B%5Crightharpoonup%7D%7BF_i%7D%7D_%5Ctext%7B%E4%B8%BB%E5%8A%A8%E5%8A%9B%7D%2B%5Cunderbrace%7B%5Coverset%7B%5Crightharpoonup%7D%7BR_i%7D%7D_%5Ctext%7B%E7%BA%A6%E6%9D%9F%E5%8A%9B%7D%2B%5Cunderbrace%7B(-m%5Cddot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D)%7D_%5Ctextbf%7B%E8%BE%BE%E6%9C%97%E8%B4%9D%E5%B0%94%E6%83%AF%E6%80%A7%E5%8A%9B%7D%3D0%2C%5Cquad%20i%3D1%2C2%2C%5Cdots%2CN)

上式左端这些力在虚位移下所做的功（称为虚功）

![TeX](https://math.jekyllwriter.com/?q=%5Cdelta%20W%3D%5Csum_%7Bi%3D1%7D%5E%7BN%7D(%5Coverset%7B%5Crightharpoonup%7D%7BF_i%7D%2B%5Coverset%7B%5Crightharpoonup%7D%7BR_i%7D-m%5Cddot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D)%5Ccdot%5Cdelta%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%3D0.)

由于虚位移除了受到约束的限制以外具有任意性，所以上式不失一般性地等价于牛顿方程和约束方程联立的方程组。

这时容易找出一类可以直接消去的约束力，它满足 ![TeX](https://math.jekyllwriter.com/?q=%5Csum_%7Bi%3D1%7D%5E%7BN%7D%5Coverset%7B%5Crightharpoonup%7D%7BR_i%7D%5Ccdot%5Cdelta%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%3D0) ,即约束力所做总虚功为零。这类约束称为理想约束，其中包括几种很常见的约束：

1.光滑曲面约束。约束力保证质点在光滑曲面上运动，其方向总是垂直于曲面，从而总是垂直于所有的虚位移。
2.刚性内力约束。两质点的相互作用保证它们距离不变，从而根据作用与反作用定律（牛顿第三定律），内力所做的总虚功为零。
3.刚性接触约束。两刚体作用力与反作用力所做虚功之和为零。

从而这类约束被直接消去，不再列写其约束方程和约束力，得到达朗贝尔原理

![TeX](https://math.jekyllwriter.com/?q=%5Csum_%7Bi%3D1%7D%5E%7BN%7D(%5Coverset%7B%5Crightharpoonup%7D%7BF_i%7D-m%5Cddot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D)%5Ccdot%5Cdelta%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%3D0.)

## 广义坐标(Generalized Coordinates)

在什么情况下，这个操作是可以完成的呢？
前文提到，有时坐标之间存在直接的约束。应用达朗贝尔原理，我们可以消去理想约束。此外，从前文几何约束的例子中我们可以看出，坐标之间的不独立性在选取坐标时就可以提前消除。

我们的力学规律是基于位矢 ![TeX](https://math.jekyllwriter.com/?q=%5Coverset%7B%5Crightharpoonup%7D%7Br%7D) 的，通过确定系统的位置与速度来预测运动（此外还要知道相互作用的形式）。现在要选取相互独立的广义坐标就要用广义坐标给出位矢，具体的表达式取决于广义坐标。在此后的推导中，我们认为这个关系是已知的一个函数： ![TeX](https://math.jekyllwriter.com/?q=%5Coverset%7B%5Crightharpoonup%7D%7Br%7D%3D%5Coverset%7B%5Crightharpoonup%7D%7Br%7D(q_1%2Cq_2%2C%5Cdots%2Cq_s)) ，其中 ![TeX](https://math.jekyllwriter.com/?q=q_%5Calpha%5Cquad(%5Calpha%3D1%2C2%2C%5Cdots%2Cs)) 是广义坐标， ![TeX](https://math.jekyllwriter.com/?q=s) 称为自由度（仅当广义坐标相互独立）。

##拉格朗日方程(Lagrange's Equations)

现在我们有了达朗贝尔原理和广义坐标，他们从不同角度消去变量（分别是约束力和坐标）。达朗贝尔原理式中涉及关于虚位移的矢量运算，而实际上我们更希望能够开始像牛顿第二定律一样直接列写微分方程，而且是列写数量足够少的、关于广义坐标的微分方程组。



由于广义坐标是相互独立的，其虚位移不受任何约束，故具有任意性。那么虚位移的系数为零就是达朗贝尔原理成立的等价条件，这样就可以从达朗贝尔原理中消去虚位移，得到微分方程。

把广义坐标表示的虚位移： ![TeX](https://math.jekyllwriter.com/?q=%5Cdelta%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%3D%5Csum_%7B%5Calpha%3D1%7D%5E%7Bs%7D%5Cfrac%7B%5Cpartial%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7B%5Cpartial%20q_%5Calpha%7D%5Cdelta%20q_%5Calpha) 代入达朗贝尔原理，并用分配率交换求和顺序：
![TeX](https://math.jekyllwriter.com/?q=%5Csum%20_%7B%5Calpha%20%3D1%7D%5EN%20%5Cleft%5B%5Csum%20_%7Bi%3D1%7D%5EN%20%5Cleft(%5Coverset%7B%5Crightharpoonup%20%7D%7BF_i%7D-m_i%5Cddot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%5Cright)%5Ccdot%20%5Cfrac%7B%5Cpartial%20%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%7B%5Cpartial%20q_%7B%5Calpha%20%7D%7D%5Cright%5D%5Cdelta%20q_%7B%5Calpha%20%7D%3D0.)
由于广义坐标是相互独立的，其虚位移不受任何约束，故具有任意性。那么虚位移的系数为零就是上式恒成立的等价条件：
![TeX](https://math.jekyllwriter.com/?q=%5Csum%20_%7Bi%3D1%7D%5EN%20%5Cleft(%5Coverset%7B%5Crightharpoonup%20%7D%7BF_i%7D-m_i%5Cddot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%5Cright)%5Ccdot%20%5Cfrac%7B%5Cpartial%20%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%7B%5Cpartial%20q_%7B%5Calpha%20%7D%7D%3D0%2C%5Cquad%5Calpha%3D1%2C2%2C%5Cdots%2Cs.)
它展开后的第一项可以定义为广义力 ![TeX](https://math.jekyllwriter.com/?q=Q_%5Calpha%3D%5Csum%20_%7Bi%3D1%7D%5EN%20%5Coverset%7B%5Crightharpoonup%20%7D%7BF_i%7D%5Ccdot%20%5Cfrac%7B%5Cpartial%20%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%7B%5Cpartial%20q_%7B%5Calpha%20%7D%7D) (如果选取笛卡尔坐标，广义力就是牛顿力学中的力)。
这时已经达到我们简化方程的“目的”，但不难注意到方程涉及矢量运算，这在许多坐标变换中是不便的。

它展开后的第二项等于负的![TeX](https://math.jekyllwriter.com/?q=%5Cfrac%7Bd%7D%7B%5Ctext%7Bdt%7D%7D%5Csum%20_%7Bi%3D1%7D%5EN%20%5Cleft(m_i%5Cdot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%5Ccdot%20%5Cfrac%7B%5Cpartial%20%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%7B%5Cpartial%20q_a%7D%5Cright)-%5Csum%20_%7Bi%3D1%7D%5EN%20%5Cleft(m_i%5Cdot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%5Ccdot%20%5Cfrac%7B%5Cpartial%20%5Cdot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%7D%7B%5Cpartial%20q_a%7D%5Cright))
，这是根据全导数的积法则 ![TeX](https://math.jekyllwriter.com/?q=%5Cfrac%7Bd%7D%7B%5Ctext%7Bdt%7D%7D%5Csum%20_%7Bi%3D1%7D%5EN%20%5Cleft(m_i%5Cdot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%5Ccdot%20%5Cfrac%7B%5Cpartial%20%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%7B%5Cpartial%20q_a%7D%5Cright)%3D%5Csum%20_%7Bi%3D1%7D%5EN%20%5Cleft(m_i%5Cddot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%5Ccdot%20%5Cfrac%7B%5Cpartial%20%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%7B%5Cpartial%20q_a%7D%5Cright)%2B%5Csum%20_%7Bi%3D1%7D%5EN%20%5Cleft(m_i%5Cdot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%5Ccdot%20%5Cfrac%7B%5Cpartial%20%5Cdot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%7D%7B%5Cpartial%20q_a%7D%5Cright)) 得到的。
从而
![TeX](https://math.jekyllwriter.com/?q=%5Cfrac%7Bd%7D%7B%5Ctext%7Bdt%7D%7D%5Csum%20_%7Bi%3D1%7D%5EN%20%5Cleft(m_i%5Cdot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%5Ccdot%20%5Cfrac%7B%5Cpartial%20%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%7B%5Cpartial%20q_a%7D%5Cright)-%5Csum%20_%7Bi%3D1%7D%5EN%20%5Cleft(m_i%5Cdot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%5Ccdot%20%5Cfrac%7B%5Cpartial%20%5Cdot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%7D%7B%5Cpartial%20q_a%7D%5Cright)%3DQ_%7B%5Calpha%20%7D.)
我们需要一个具有特殊特性的标量代替位矢。实际上，上式左边的两项可以从动能![TeX](https://math.jekyllwriter.com/?q=T%3D%5Cfrac%7B1%7D%7B2%7D%5Csum_%7Bi%3D1%7D%5E%7BN%7Dm_i%5Cdot%7B%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%3DT(q_1%2Cq_2%2C%5Cdots%2Cq_s%3B%5Cdot%7Bq_1%7D%2C%5Cdot%7Bq_2%7D%2C%5Cdots%2C%5Cdot%7Bq_s%7D%3Bt))得到：

![TeX](https://math.jekyllwriter.com/?q=%5Cfrac%7B%5Cpartial%20T%7D%7B%5Cpartial%5Cdot%7Bq%7D_%5Calpha%7D%3D%5Csum_%7Bi%3D1%7D%5E%7BN%7D%5Cfrac%7B%5Cpartial%20T%7D%7B%5Cpartial%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7D%5Ccdot%5Cfrac%7B%5Cpartial%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7D%7B%5Cpartial%5Cdot%7Bq%7D_%5Calpha%7D%3D%5Csum_%7Bi%3D1%7D%5E%7BN%7Dm_i%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%5Ccdot%5Cfrac%7B%5Cpartial%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7D%7B%5Cpartial%20%5Cdot%7Bq%7D_%5Calpha%7D%20%2C)
![TeX](https://math.jekyllwriter.com/?q=%5Cfrac%7B%5Cpartial%20T%7D%7B%5Cpartial%7Bq_%5Calpha%7D%7D%3D%5Csum_%7Bi%3D1%7D%5E%7BN%7D%5Cfrac%7B%5Cpartial%20T%7D%7B%5Cpartial%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7D%5Ccdot%5Cfrac%7B%5Cpartial%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7D%7B%5Cpartial%7Bq%7D_%5Calpha%7D%3D%5Csum_%7Bi%3D1%7D%5E%7BN%7Dm_i%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%5Ccdot%5Cfrac%7B%5Cpartial%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7D%7B%5Cpartial%20q_%5Calpha%7D%20.)
容易验证![TeX](https://math.jekyllwriter.com/?q=%5Cfrac%7B%5Cpartial%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7D%7B%5Cpartial%20%5Cdot%7Bq%7D_%5Calpha%7D%3D%5Cfrac%7B%5Cpartial%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7B%5Cpartial%20q_%5Calpha%7D)$ ，也就有 ![TeX](https://math.jekyllwriter.com/?q=%5Cfrac%7B%5Cpartial%20T%7D%7B%5Cpartial%5Cdot%7Bq%7D_%5Calpha%7D%3D%5Csum_%7Bi%3D1%7D%5E%7BN%7D%5Cfrac%7B%5Cpartial%20T%7D%7B%5Cpartial%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7D%5Ccdot%5Cfrac%7B%5Cpartial%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7D%7B%5Cpartial%5Cdot%7Bq%7D_%5Calpha%7D%3D%5Csum_%7Bi%3D1%7D%5E%7BN%7Dm_i%5Cdot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%5Ccdot%5Cfrac%7B%5Cpartial%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D%7B%5Cpartial%20q_%5Calpha%7D.)

用这些含有动能的表达式替换掉原来方程的坐标，有
![TeX](https://math.jekyllwriter.com/?q=%5Cfrac%7Bd%7D%7Bdt%7D%5Cfrac%7B%5Cpartial%20T%7D%7B%5Cpartial%5Cdot%7Bq%7D_%5Calpha%7D-%5Cfrac%7B%5Cpartial%20T%7D%7B%5Cpartial%20q_%5Calpha%7D%3DQ_%5Calpha%2C%5Cquad%5Calpha%3D1%2C2%2C%5Cdots%2Cs%20%EF%BC%8C)

这就是拉格朗日方程。



如果主动力是保守力，也就是说 ![TeX](https://math.jekyllwriter.com/?q=%5Coverset%7B%5Crightharpoonup%7D%7BF_i%7D%3D-%5Cfrac%7B%5Cpartial%20V%7D%7B%5Cpartial%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D) （其中 V 是势能），那么广义力也有类似形式 ![TeX](https://math.jekyllwriter.com/?q=Q_%5Calpha%3D%5Csum%20_%7Bi%3D1%7D%5EN%20(-%5Cfrac%7B%5Cpartial%20V%7D%7B%5Cpartial%5Coverset%7B%5Crightharpoonup%7D%7Br_i%7D%7D)%5Ccdot%20%5Cfrac%7B%5Cpartial%20%5Coverset%7B%5Crightharpoonup%20%7D%7Br_i%7D%7D%7B%5Cpartial%20q_%7B%5Calpha%20%7D%7D%3D-%5Cfrac%7B%5Cpartial%20V%7D%7B%5Cpartial%20q_%5Calpha%7D) ，从而拉格朗日方程可以写为 ![TeX](https://math.jekyllwriter.com/?q=%5Cfrac%7Bd%7D%7Bdt%7D%5Cfrac%7B%5Cpartial%20T%7D%7B%5Cpartial%5Cdot%7Bq%7D_%5Calpha%7D-%5Cfrac%7B%5Cpartial%20(T-V)%7D%7B%5Cpartial%20q_%5Calpha%7D%3D0) 。

我们知道一般情况下，势能和广义速度 ![TeX](https://math.jekyllwriter.com/?q=%5Cdot%7Bq%7D_%5Calpha) 无关，即 ![TeX](https://math.jekyllwriter.com/?q=%5Cfrac%7B%5Cpartial%20V%7D%7B%5Cpartial%5Cdot%20q_%5Calpha%7D%3D0) 。于是可以把拉格朗日方程写为

![TeX](https://math.jekyllwriter.com/?q=%5Cfrac%7Bd%7D%7Bdt%7D%5Cfrac%7B%5Cpartial%5Cmathcal%7BL%7D%7D%7B%5Cpartial%5Cdot%7Bq%7D_%5Calpha%7D-%5Cfrac%7B%5Cpartial%5Cmathcal%7BL%7D%7D%7B%5Cpartial%20q_%5Calpha%7D%3D0%2C%5Cquad%5Calpha%3D1%2C2%2C%5Cdots%2Cs.)

这就是保守体系的拉格朗日方程，其中 ![TeX](https://math.jekyllwriter.com/?q=%5Cmathcal%7BL%7D%3DT-V) 称为拉格朗日函数或者拉格朗日量。

不难发现，不仅限于保守力，对于形式如 ![TeX](https://math.jekyllwriter.com/?q=Q_%5Calpha%3D-%5Cfrac%7B%5Cpartial%20U(q%2C%5Cdot%7Bq%7D)%7D%7B%5Cpartial%20q_%5Calpha%7D%2B%5Cfrac%7Bd%7D%7Bdt%7D%5Cfrac%7B%5Cpartial%20U(q%2C%5Cdot%7Bq%7D)%7D%7B%5Cpartial%20%5Cdot%7Bq_%5Calpha%7D%7D) 的相互作用，上式同样能够描述，这个关于广义坐标、广义速度的函数 ![TeX](https://math.jekyllwriter.com/?q=U(q%2C%5Cdot%7Bq%7D)) 称为广义势能。
实际上，电磁力正是一类可以化为上述广义势能形式的相互作用，用电势 ![TeX](https://math.jekyllwriter.com/?q=%5Cvarphi) 和磁矢势 ![TeX](https://math.jekyllwriter.com/?q=%5Coverset%7B%5Crightharpoonup%7D%7BA%7D) 可以写出包含这一广义势能函数的拉格朗日函数 ![TeX](https://math.jekyllwriter.com/?q=%5Cmathcal%7BL%7D%3D%5Cfrac%7B1%7D%7B2%7Dm%5Coverset%7B%5Crightharpoonup%7D%7Bv%7D%5E2-e%5Cvarphi%2Be%5Coverset%7B%5Crightharpoonup%7D%7Bv%7D%5Ccdot%5Coverset%7B%5Crightharpoonup%7D%7BA%7D) ，相应的运动方程是 ![TeX](https://math.jekyllwriter.com/?q=m%5Cddot%7B%5Coverset%7B%5Crightharpoonup%7D%7Br%7D%7D%3De(%5Coverset%7B%5Crightharpoonup%7D%7BE%7D%2B%5Coverset%7B%5Crightharpoonup%7D%7Bv%7D%5Ctimes%5Coverset%7B%5Crightharpoonup%7D%7BB%7D)) .

##  
注：有些概念是现场定义的、甚至没有定义，因为先按直觉理解也无妨。
注：文中的“广义坐标”一直指代的是先前选取的独立的广义坐标，称为第II类广义坐标。实际上，广义坐标也可以是不独立的，笛卡尔坐标也是广义坐标。

##总结

我们从牛顿力学出发，先利用虚位移的概念预先消去一类常见的约束——理想约束，从而得到达朗贝尔原理，这时之前已经消去的约束方程蕴含在虚位移有限的任意性中。

之后利用独立的广义坐标，从达朗贝尔原理（广义坐标形式）出发，先利用广义坐标的独立性消去虚位移，这时之前已经消去的约束方程蕴含在广义坐标的独立性中。

再利用动能这一标量函数消去位矢这一矢量，并把广义力用势能表示，从而得到关于广义坐标的标量微分方程——拉格朗日方程，它的分析对象是（类）能量。