---
title: "IP置换"
tags:
- crypto
---

IP置换 $IP(x)$ 与 IP逆置换 $IP^{-1}(x)$ 用于 [DES](/crypto/DES.md) 的明文处理的第一步和密文处理的最后一步。

此过程只是简单的数据位交换，对于[DES](/crypto/DES.md) 的安全性并没有提高。

其过程可以使用下图简单的进行表示：

![IP pic](https://img.gejiba.com/images/f85131bcb32e980acef55fa528725200.png)

下表给出了初始置换 $IP$ 的映射表格：
|    |    |    |    |    |    |    |    |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 58 | 50 | 42 | 34 | 26 | 18 | 10 | 2 |
| 60 | 52 | 44 | 36 | 28 | 20 | 12 | 4 |
| 62 | 54 | 46 | 38 | 30 | 22 | 14 | 6 |
| 64 | 56 | 48 | 40 | 32 | 24 | 16 | 8 |
| 57 | 49 | 41 | 33 | 25 | 17 | 9  | 1 |
| 59 | 51 | 43 | 35 | 27 | 19 | 11 | 3 |
| 61 | 53 | 45 | 37 | 29 | 21 | 13 | 5 |
| 63 | 55 | 47 | 39 | 31 | 23 | 15 | 7 |

 此映射表格从左至右、从上至下，依次表示每一个位对于的置换后的位置。假如我们需要置换第  10 位，我们可以简单的数表格，得到第 10 位应当置换到第 52 位。

下表展示了 $IP^{-1}$ 的映射表格，其与上文给出的初始置换表格的置换完全相反。

| ||||||||
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|40|8|48|16|56|24|64|32|
|39|7|47|15|55|23|63|31|
|38|6|46|14|54|22|62|30|
|37|5|45|13|53|21|61|29|
|36|4|44|12|52|20|60|28|
|35|3|43|11|51|19|59|27|
|34|2|42|10|50|18|58|26|
|33|1|41|9|49|17|57|25| 

上述置换在软件实现上具有一定的复杂性，但在硬件实现上较为简单。由于[DES](crypto/DES.md) 的设计具有相当的黑箱性质，关于此置换存在的原因，我们不得而知，可能是为了更好的数据读取。