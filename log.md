## 



## 推导过程

**主要参考文献：**

On Planar Shape Interpolation With Logarithmic Metric Blending [2025]

Planar Shape Interpolation with Bounded Distortion [2013]

Bounded Distortion Tetrahedral Metric Interpolation [2019]


**动机：**

1.将On Planar Shape Interpolation With Logarithmic Metric Blending给出的度量混合方法就其数学形式进行推广，目前有两种推广形式

- $ g_w=\exp(\sum_{i=0}^{n}w_i\log g_i) $
- $ \sum_{i=0}^{n}w_i\log(g_w^{-1/2}g_ig_w^{-1/2})=0 $

我们可以证明，这两种混合方法都可以在混合步骤实现对共形失真和面积失真的有界控制，具体形式为
$$
K_w\leqslant\prod_{i=0}^{n}K_i^{w_i},\quad D_w=\prod_{i=0}^{n}D_i^{w_i}
$$
我们还可以证明，在连续情形下，这两种混合方法在共形映射下得到的混合度量是平坦度量。

这两种方法目前有显著的计算差异，目前的实验也显示，两种混合所得到的混合度量在数值上接近，在混合阶段所对应的失真也几乎完全一致

2.除了上述方法，我们还可以在数学上设想其他的混合方法。实际上，我们可以将上述混合理解为度量矩阵的某种加权平均值计算，则我们还可以定义如下平均值

- $ g_w=H^{1/2}(H^{-1/2}AH^{-1/2})^{1/2}H^{1/2} $

其中$ A = \sum_{i=0}^{n}w_ig_i,\quad H = (\sum_{i=0}^{n}w_i g_i^{-1})^{-1} $

- $ \sum_{i=0}^{n}w_i((g_w+g_i)/2)^{-1}=g_w^{-1} $

实验显示，这两种方法很可能也能控制面积失真和共形失真，不过它们并不是On Planar Shape Interpolation With Logarithmic Metric Blending给出的度量混合方法的推广，在论文相应的情形下所得到的度量不同，与前文提到的混合度量方法相比，其在控制失真方面表现出的性能并不与之相同，且随着权重向量的变化相对大小关系也会发生变化

但是，这两种方法似乎并没有在共形映射下混合得到平坦度量的性质

**实现：**

- [] MATLAB：参考Bounded Distortion Tetrahedral Metric Interpolation的开源代码


**Todo：**

- [] 使用等距优化实现度量平坦化步骤，具体实现参考Bounded Distortion Tetrahedral Metric Interpolation及其开源代码
- [] 在前一步的基础上进行实验，计算共性共形失真和面积失真，考察效果
- [] 对度量混合步骤的计算进行并行化加速
- [] 实验验证共形映射下，对数欧式混合和karcher均值混合所得到的度量是平坦度量
- [] 进一步考虑是否能够得出在更一般的情形下能够得到平坦混合度量且有界控制失真的方法，彻底排除平坦化步骤带来的失真。



## 写作的中文部分

## Abstract

## Introduction

**要点**

- [x] 清晰的介绍（贡献如何，新颖性、独创性程度）（决定审稿人要不要看下去）
- [x] 详细的相关工作（尽量多引用，不能侮辱前人方法）（不能只是清单，要结合当前工作）
- [x] 清晰地解释方法（逻辑清晰，让外行人看懂）（让读者可复现）（讨论到达答案的过程）（符号简单）
- [x] 展现特别的结果（讨论任何 limitation，引出Future Work）
- [x] 论文给别人看
- [ ] 写完后参考How to write修改一遍（[16年教程](https://vitalight.me/upload/2021/03/RE00-How-to-Write-a-SIGGRAPH-Paper-7e2a071d1fa64145bdba16fee093aca7.pdf)）



提交前检查

- [x] 作者
- [x] CCS Concept / keywords
- [x] 是否有理论上的错误？
- [x] Bézier
- [x] 优化步骤删减掉（放到附加材料中）
- [x] 找图片（动画，漫画，形变，设计图，图案）
- [x] inverse 要求边界不能有自交
- [x] 哪些公式需要有标号
- [ ] 公式简化和美化
- [x] 引用格式
- [x] 缩写检查 (PGC, GC)
- [x] 图像字体
- [x] 提交用的版本？
- [x] 各种结果的颜色挑选
- [x] 说明Cauchy和Green的等价性
- [x] title 标号替换
- [x] 删减页数
- [x] 如何sample 内部点
- [x] Gauss积分(也一阶收敛，不提了)
- [x] barycentric
- [x] 作图：细节



Latex 语法

- [ ] {\itshape very} 斜体
- [ ] ``camera-ready'' 引号
- [ ] \---  长横线—
- [ ] \url{https://www.acm.org/publications/proceedings-template} 超链接
- [ ] 内联代码块 \begin{verbatim}
- [ ] 代码显示 \verb|\vspace|
- [ ] 粗体 {\bfseries Your document will be returned to you for revision if modifications are discovered.}
- [ ] 表格 table 双列表格 table*
