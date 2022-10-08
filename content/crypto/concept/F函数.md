---
title: "F函数"
---

f函数的处理流程图如下：

![F function](https://img.gejiba.com/images/9b61d89173644a8f48be626c3a881165.png)

其中，参数含义为：
	$R_{i-1}$ 上一轮加密获得的右半部分 32 bit
	$k_i$ [[crypto/concept/DES密钥编排|密钥编排]]获得的 48 bit 密钥

当获得 32 bit 的 $R_{i-1}$ 时，我们发现长度显然与 $k_i$ 的长度不符，所以我们需要拓展 $R_{i-1}$ ，故而使用了$E(R_{i-1})$ [[crypto/concept/E置换|扩展置换]]。

将扩展置换后的结果与[[crypto/concept/DES密钥编排|密钥编排]]后的$k_i$进行异或(XOR)操作，获得 48 bit 输出。我们将输出以 6 bit 为一组推入 [[crypto/concept/S-盒|S-盒]] 获得 32 bit 输出。

最后，我们将 [[crypto/concept/S-盒|S-盒]] 的输出汇总后输入 [[crypto/concept/置换P|置换P]]  获得最终 32 bit 输出。