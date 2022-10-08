---
title: "密钥编排"
---

密钥编排接受 64 bit 长度的密钥（实际长度为 56 bit ）将其生成 16 轮加密流程中使用的 48 bit 密钥。结构图如下：

![Key Struct](https://img.gejiba.com/images/b95a0a7d704430e74805f2562756c701.png)

我们首先使用 `PC-1` 去除校验位并进行密码重排，使用的表格如下：

![PC-1 Table](https://img.gejiba.com/images/52fecb8d9d0abd016c7f7a7edc3136bb.png)

将获得的 56 bit 的输出分为 $C_0$ 和 $D_0$ 部分，接下来我们使用$LS_i$函数进行移位操作，具体规定如下：

1. 当 $i = 1, 2, 9, 16$时，$LS_i$表达向左移动 1 位
2. 当 $i \not = 1, 2, 9, 16$时，$LS_i$表示向左移动 2 位

简单计算左移位数 $4*1 + 12 * 2 = 28$ ，恰好为 $C_i$ 或 $D_i$ 的位数。这带了一个极其有用的特性，即$C_0 = C_{16}$ 和 $D_0 = D_{16}$ ，这对于[[crypto/DES#解密|解密]]密钥编排非常有用。

最终，我们将生成的 $L_i$ 和 $D_i$ 拼接起来，并根据`PC-2`表格进行替换，表格如下：

![PC-2 Table](https://img.gejiba.com/images/ff7e639951e23e17b48e0bc4da3148ce.png)

由此，我们可以得到第 $i$ 轮所需要的密钥