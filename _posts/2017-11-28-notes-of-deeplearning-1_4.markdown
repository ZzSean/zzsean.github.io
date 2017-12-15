---
layout:     post
title:      "Notes of DeepLearning 1_4"
subtitle:   " 深层神经网络 "
date:       2017-11-28 14:32:23
author:     "Zz"
header-img: "img/default-bg.jpeg"
catalog: false
tags:
    - deep learning
---

深度学习第一课第四周的笔记---深层神经网络|

## 前向传播
	
Input:  \\(a^{[l-1]}\\)
	
Output: \\(a^{[l-1]}\\), cache \\(z^{[l]}\\)

* 公式

\\[z^{[l]}= W^{[l]}\cdot a^{[l-1]}+b^{[l]}\\\ a^{[l]}=g^{[l]}(z^{[l]})\\]

* 向量化程序

\\[Z^{[l]}=W^{[l]}\cdot A^{[l-1]}+b^{[l]}\\\A^{[l]}=g^{[l]}(Z^{[l]})\\]

## 反向传播

Input:  \\(da^{[l]}\\)

Output: \\(da^{[l-1]}，dW^{[l]}，db^{[l]}\\)

* 公式

\\[dz^{[l]}=da^{[l]} * g^{[l]'}(z^{[l]})\\\dW^{[l]}=dz^{[l]}\cdot a^{[l-1]}\\\db^{[l]}=dz^{[l]}\\\da^{[l-1]}=W^{[l]}{^T}\cdot dz^{[l]}\\]

* 向量化程序

\\[dZ^{[l]}=dA^{[l]} * g^{[l]'}(Z^{[l]})\\\dW^{[l]}=\dfrac{1}{m}dZ^{[l]}\cdot A^{[l-1]}\\\db^{[l]}=\dfrac{1}{m}np.sum(dZ^{[l]},axis=1,keepdims = True)\\\dA^{[l-1]}=W^{[l]}{^T}\cdot dZ^{[l]}\\]
