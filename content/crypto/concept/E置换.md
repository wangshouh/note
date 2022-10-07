---
title: "扩展置换E"
---

$E(R_{i-1})$ 拓展置换的目的是将 32 bit 的 $R_{i-1}$输入扩展为 48 bit

置换的示意图如下：

![E Chart](https://img.gejiba.com/images/c353f2c77c64ffb8e5c66e9161d218ea.png)

完整的置换表格可以参考下表：

![E Table](https://acjgpfqbqr.cloudimg.io/_cat_/ncdf1m.jpg)

通过表格，我们可以发现我们复用了32、4、8、12、16、20、24、28、5、9、13、17、21、25、29、1位的数据，共计 16 位，实现了 32 bit 到 48 bit 的扩展置换。