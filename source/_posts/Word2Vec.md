---
title: Word2Vec
date: 2021-06-22 21:03:52
tags:
categories:
- [Technical, Machine Learning]
---


## Word2Vec 一个经典的自然语言处理模型

Word2Vec的目标是**根据语料库把词转换成一个描述词的向量**。一个经典的例子是`Vector(king) - Vector(man) + Vector(woman) ~ Vector(queue)`。

本文参考：
> https://medium.com/@vishwasbhanawat/the-architecture-of-word2vec-78659ceb6638
> https://jalammar.github.io/illustrated-word2vec/
> https://code.google.com/archive/p/word2vec/
> https://towardsdatascience.com/an-implementation-guide-to-word2vec-using-numpy-and-google-sheets-13445eebd281

<!--more-->

### 训练数据如何生成

#### CBOW and Skip-gram

训练数据的生成与**语言模型**有关。有两种生成训练数据的方法：

第一种方式的input word与target word是包含与被包含的关系，比如对于句子`by a red bus in`，其中`red`是target，其它四个词是input。这种方式叫做**Continuous Bag of Words**

第二种方式正相反，同样一个例子中，其它四个词是input，而`red`是output。这种方式叫做**Skipgram**

实际上训练数据需要一步转换来更方便计算机训练，以上述的第二种方式为例，转换前的数据和转换后的数据如下图所示：

{% asset_img word2vec-training-dataset.png %}

#### Negtive Sampling

往训练数据中增加随机的标签为0的数据，以防止模型过拟合。

### 谷歌Word2Vec模型

下图展示了一个简版的网络，其中共有9个词，生成的vector共有10个元素
{% asset_img network.png %}

### 模型原理

以神经网络的角度来看，模型的最终预测结果是一个词附近各个词出现的概率。而前一层则总结了这个词的特征。如果两个词比较像，那么前后的词也应该比较像，故描述这两个词的特征向量应该比较像，这就是embeding的原理。
