---
title: "DES"
tags:
- crypto
---

## 加密

`AES`要求密钥长度为`128`位，具体加密流程图如下：

![AES Encrypt](https://img.gejiba.com/images/ee7ac3f69bd95ccff31124101a35f7cd.png)

上图展示了`AES`加密的整体流程，接下来，我们简单介绍每一层的作用：

1. **密钥加法层** 使用密钥编排得到的子密钥与输入明文$x$进行`XOR`异或计算
2.  **字节代换层** 使用具有特殊数学性质的查找表对数据进行非线性变换，保证对单个状态的修改可以迅速传播到整个数据路径中
3. 扩散层
	- ShiftRows 行移位变化 在位级别进行数据置换
	- MixColumn 列混淆变化是一个[[crypto/concept/混淆与扩散#混淆（Confusion）|混淆]]操作，合并了长度为 4 字节的分组

一个更具可视化的展示图如下：

![Round Function](https://acjgpfqbqr.cloudimg.io/_cat_/8g3at2.png)

