---
title: "DES"
tags:
- crypto
---

本页面主要介绍`DES`算法，`DES`是一种使用 56 位密钥(实际上，我们一般看到 64 位的密钥中有 8 位校验位无法参与加密)对 64 位长分组进行加密的密码。

其具体加密给出的流程图如下:

![DES Flow](https://img.gejiba.com/images/faed068123175795e20491afa18d9bb8.png)

上述步骤可用文字表述如下:

1. 明文 $x$ 首先进入[初始置换](concept/ip.md) $IP(x)$

上述结构被称为`Feistel 网络`，其数学表达形式如下:
$$
L_i = R_{i-1}
R_i = L_{i-1} \oplus f(R_{i-1}, k_i)
$$

其中，各参数的含义均可以在`Ferstel 网络`的结构图中获得。

