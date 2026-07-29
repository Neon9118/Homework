# 第二次培训学习报告

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/picture/cover.png)


> **课程**：研究生培训课
> **提交格式**：Markdown
> **作业内容**：7.22 & 7.24课堂内容回顾/ Git基本操作和远程仓库 / 实验环境及Linux环境下的基本使用 / 现有的模型架构及使用/机器学习/python下怎么使用numpy和scipy/现有的AI模型分类/matlab使用
> **报告人**：刘欣雨

---

## 目录

- [第二次培训学习报告](#第二次培训学习报告)
  - [目录](#目录)
- [](#)
- [第五部分：AI模型方法体系——机器学习与深度学习](#第五部分ai模型方法体系机器学习与深度学习)
  - [一、机器学习](#一机器学习)
    - [1.1 配置环境：安装Anaconda+Pycharm](#11-配置环境安装anacondapycharm)
    - [1.2 线性回归](#12-线性回归)
    - [1.3 逻辑回归](#13-逻辑回归)
    - [1.4 KNN](#14-knn)
    - [1.5 决策树](#15-决策树)
    - [1.6 支持向量机](#16-支持向量机)
  - [二、深度学习](#二深度学习)
    - [2.1 配置深度学习环境：CPU版PyTorch+Anaconda](#21-配置深度学习环境cpu版pytorchanaconda)
    - [2.2 基本数学运算](#22-基本数学运算)
    - [2.3 线性回归](#23-线性回归)
    - [2.4 softmax回归](#24-softmax回归)
    - [2.5 多层感知机](#25-多层感知机)
    - [2.6 卷积神经网络](#26-卷积神经网络)
    - [2.7 现代卷积神经网络](#27-现代卷积神经网络)
- [第六部分：python下怎么使用numpy和scipy](#第六部分python下怎么使用numpy和scipy)
- [第七部分：画图](#第七部分画图)
  - [一、matplotlib](#一matplotlib)
  - [二、matlab](#二matlab)
  - [三、Graphviz](#三graphviz)
  
---

# 


-



---


---
---
# 第五部分：AI模型方法体系——机器学习与深度学习


>机器学习是框架-方法，深度学习是顶层-工程突破。
>此部分在报告中主要以概念和原理为主，==详细实操见附件1，2==，附件1中的练习源于本科《机器学习》实验课，附件2中的练习源于《动手学深度学习-PyTorchh（第二版）》，需要用到的数据集也全都push到GitHub里。

>也可以直接点击查看[附件1_机器学习](https://nbviewer.org/github/Neon9118/Homework/blob/main/%E7%A0%940/%E5%88%98%E6%AC%A3%E9%9B%A8_%E4%BD%9C%E4%B8%9A2/Machine_Learning_test.ipynb)，[附件2_深度学习](https://nbviewer.org/github/Neon9118/Homework/blob/main/%E7%A0%940/%E5%88%98%E6%AC%A3%E9%9B%A8_%E4%BD%9C%E4%B8%9A2/Deep_learning_test.ipynb)

## 一、机器学习

### 1.1 配置环境：安装Anaconda+Pycharm

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/picture/Anaconda.png)

<br/>

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/picture/Anaconda2.png)

<br/>

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/picture/Pycharm.png)

<br/>

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/picture/jupyternotebook.png)


<br/>

### 1.2 线性回归

- **概念**
  
- **核心原理**

- **训练评估数值**
· 概念：预测连续数值（如房价、温度）。假设输入特征与输出存在线性关系。
· 核心原理：找到一条直线（或超平面），使得所有样本点到这条线的垂直距离（残差）的平方和最小。求解方式有最小二乘法（正规方程）和梯度下降法。
· 关键注意事项：对异常值极其敏感（一个离群点能把直线带偏）；要求特征之间不能高度相关（多重共线性），否则系数不稳定；特征需做标准化/归一化（梯度下降收敛更快）。
· 训练评估指标：


<br/>







<br/>

### 1.3 逻辑回归

- **概念**
  
- **核心原理**

- **训练评估数值**

<br/>


<br/>

### 1.4 KNN

- **概念**
  
- **核心原理**

- **训练评估数值**

<br/>



### 1.5 决策树

- **概念**
  
- **核心原理**

- **训练评估数值**

<br/>

- **决策树可视化**

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/picture/tongji3.png)

<br/>

### 1.6 支持向量机

- **概念**
  
- **核心原理**

- **训练评估数值**

<br/>





---


## 二、深度学习

### 2.1 配置深度学习环境：CPU版PyTorch+Anaconda

![](f:/personal/Desktop/Homework/研0/刘欣雨_作业2/picture/sd1.png)

<br/>


### 2.2 基本数学运算

<br/>

### 2.3 线性回归

- **从零开始**
  
- **简洁实现**






<br/>


### 2.4 softmax回归

- **从零开始**
  
- **简洁实现**




<br/>


### 2.5 多层感知机

<br/>

- **从零开始**
  
- **简洁实现**


### 2.6 卷积神经网络


<br/>


### 2.7 现代卷积神经网络

<br/>


---

# 第六部分：python下怎么使用numpy和scipy



---

# 第七部分：画图

## 一、matplotlib

---

## 二、matlab

---

## 三、Graphviz