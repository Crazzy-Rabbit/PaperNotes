### 📄 New approaches to population stratification in genome-wide association studies
**原文链接**: https://www.nature.com/articles/nrg2813 (DOI: 10.1038/nrg2813) \
**作者**: Alkes L. Price, Noah A. Zaitlen, David Reich, Nick Patterson  \
**期刊**: *Nat Rev Genet*, 2010 \
**关键词**: GWAS, population stratification, mixed models, ancestry correction, cryptic relatedness  

---

## 🧠 一、研究背景

- 在进行全基因组关联研究（GWAS）时，case control在祖先结构上的差异（population stratification）会引入混杂 (confounding) 效应，导致假阳性关联。
- 以往的纠正方法多基于推断样本的遗传祖先（如 PCA 校正、结构分析等），在只有简单人口结构的情形下表现良好；但在样本中同时存在家系结构（family structure）或隐性亲缘关系（cryptic relatedness）时，上述方法可能不足以校正偏倚。 
- 本文综述近年来在纠正这种更复杂结构下（即兼顾多种混杂结构）的方法进展。

---

## 🔬 二、研究方法（综述中讨论的方法）

文中主要讨论了一些方法思路、模型框架、算法改进等，而不是新的实证研究。以下为其核心技术路线与关键点总结：

| 方法 / 思路 | 主要思想 / 机制 | 优势 & 局限 |
|--------------|-------------------|----------------------|
| PCA 校正 / 祖先得分（Ancestry inference） | 利用主成分分析（PCA）或类似方法从基因型数据中推断样本的祖先成分，并将主成分作为协变量纳入模型 | 简单、易用、在结构不复杂的样本中效果不错；但可能无法捕捉更复杂的相关性结构 |
| 线性混合模型（Linear mixed models, LMM） | 将样本间的遗传相似性（由所有标记估算的亲缘关系矩阵 / kinship matrix）作为随机效应加入模型，以控制样本间相关性 / 混杂 | 在存在隐性相关性或样本结构时有较好性能 |
| 混合模型 + PCA 协变量联合建模 | 在 LMM 中同时加入主成分作为固定效应，以补充 LMM 的不足 | 能更好校正某些极端分化标记或异常块状结构 |
| 优化亲缘矩阵估算策略 | 例如用第一主成分计算外积矩阵、或只用“高度分化标记”（unusually differentiated markers, UDMs）来构建亲缘矩阵 | 针对那些特别分化的标记可以减小模型偏差，但这些标记通常事先未知，识别较难 |

此外，作者还讨论了模拟策略设计、P–P 图 (Probability–Probability plots) 在评估校正效果中的用途，以及未来可能的改进方向。

---

## 🧩 三、主要发现
文章的几个核心观点或结论（作者在综述中的总结与讨论）：

1. 在只有一般人口结构的情形下，传统的 PCA 校正方法效果已经较好，但在样本中同时存在家系结构或隐性亲缘关系时，则需要更复杂模型的支持。\
2. 线性混合模型（LMM）在控制样本结构方面表现出色，尤其对于隐性相关性有较好的处理能力；但在少数极端分化标记 (UDMs) 存在时，其校正能力可能存在缺陷。\
3. 将 PCA 协变量与 LMM 结合使用可以弥补两者的短板，在实务分析中通常是一个有效策略。作者指出：有些异常分化标记若未被模型所“捕捉”，会导致残余偏差。\
4. 构建亲缘矩阵（kinship matrix）的方式对 LMM 的性能至关重要：如果亲缘矩阵不能很好反映样本之间的真实结构，那么 LMM 的校正效果可能受损。作者提出可以用第一主成分作外积，或者尽可能识别 UDMs 来改进亲缘矩阵。\
5. 模拟评估结果表明：在没有极端分化标记时，LMM 与 PCA 校正差异不大；但在存在这些标记的情境下，如果不加以处理，假阳性率可能被高估。作者建议，在实际 GWAS 分析中应警惕这个问题。\
6. 未来展望：识别异常分化标记、构建更鲁棒的混合模型、改进计算效率以及在更复杂样本结构（如 admixed populations）中的应用，是未来研究方向。

---

## 💬 四、个人理解与启发
- 这篇综述对 GWAS 中`人口结构偏倚`问题及其校正方法（尤其是混合模型与 PCA 结合策略）做了很好的总结，非常适合作为分析方法选型时的参考。  
- 在研究中，如果要做跨种群、或有潜在隐性亲缘结构的数据集（例如野外样本、不同群体混合采样等），就要特别注意这种混杂结构的影响。  


---

## 📚 五、参考引用
> Price, A., Zaitlen, N., Reich, D. *et al.* New approaches to population stratification in genome-wide association studies. *Nat Rev Genet*  11, 459–463 (2010). https://doi.org/10.1038/nrg2813
---

*最后更新：2025-10-17*
