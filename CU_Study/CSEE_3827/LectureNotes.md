# 01. Overview
暂无

---
# 02. Information Representation
进制：
- 十进制
- 八进制
- 二进制
- 十六进制

码制：
- 原码
- 反码
- 补码

格雷码
![[Pasted image 20240723224339.png]]

---
# 03. Boolean Algebra
表示一个boolean expression有两种常规方式：
1. SOP, sum of products:
	logical AND表示，例如XYZ
2. POS, product of sums
	logical OR表示，例如A+B+C

考虑复习Boolea Algebra的运算定律

Minterm/Maxterm，用truth table得到
![[Pasted image 20240723225920.png]]
![[Pasted image 20240723225525.png]]

但是standard form不是minimal form
同时，minterm和maxterm是可以用DeMorgan's Law相互转换的
不过有什么方式可以方便求解minterm/maxterm呢？考虑K-maps
![[Pasted image 20240723232511.png]]
如果有需要可以详细看一下kmaps相关示例
[[3_booleanAlgebra.pdf#page=36&selection=0,9,0,9|3_booleanAlgebra, page 36]]
[[3_booleanAlgebra.pdf#page=37&selection=0,28,0,28|3_booleanAlgebra, page 37]]

## Glitches and hazards
什么是glitches？电路输出的非预期的变化
什么是hazard？会引发glitches的硬件结构
如何避免呢？同步设计和extra implicants

# 04. 

