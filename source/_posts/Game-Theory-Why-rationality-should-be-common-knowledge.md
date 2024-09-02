---
title: 'Game Theory: Why rationality should be common knowledge?'
date: 2024-09-02 10:49:31
tags: 
- Game Theory
categories:
- Micro Econ
- Game Theory
---

# An example

{% asset_img example.png This is an example image %}

# Analysis

## Backward Induction

逆向归纳法解得：
- 第三阶段，Player1选择L''
- 第二阶段，Player2选择L'
- 第一阶段，Player1选择L

这一解要求理性是 common knowledge ，如果理性不是 common knowledge 会发生什么？

## 1是理性的是共同知识，2是理性的不是共同知识

- Player2内心想法：
	- 如果博弈进行到第二阶段，理性的Player1会在第三阶段选L''
	- 可是博弈真进行到第二阶段，2会认为Player1在第一阶段是非理性的不是吗？
	- 答案并不是。即使Player1第一阶段选了R，2仍觉得他可能是理性的。原因在于，1如果认为2不是理性的，那么1是有动机选R的，2有可能非理性的选R'，从而1有可能在第三阶段选L''
	- 所以2不能指望1在3阶段选R''，因为1可能在诱导2在第二阶段选R'，因为2是否理性不是公共知识

所以outcome很有可能是进入到第二阶段，2在第二阶段选L'

## 2是理性的是共同知识，1是理性的不是共同知识

- Player1的内心想法：
	- 如果第一阶段选R，2可能认为1是非理性的，因为1是理性的不是公共知识
	- 通过在第一阶段选R，2认为1是非理性的，可能会在第二阶段选R'，希望1在第三阶段选R'
	- 在第三阶段选L''获得3

所以outcome很有可能是进入到第三阶段，1在第三阶段选L''

# Another example

在可以使用IESDS得到唯一解的普通囚徒困境当中，为什么要求双方理性是common knowledge？

- 如果A理性是共识，B理性不是，那么A可能选择合作以期待B选择合作。A的理性体现在他没有排除B是非理性的可能性
