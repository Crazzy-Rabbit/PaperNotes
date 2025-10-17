### 📄  Common SNPs explain a large proportion of the heritability for human height
**原文链接**: https://www.nature.com/articles/ng.608 (DOI: 10.1038/nrg2813) \
**作者**: Yang, J., Benyamin, B., McEvoy, B. et al.  \
**期刊**: *Nat Genet*, 2010 \
**关键词**: heritability, common SNPs, missing heritability, mixed model, genetic relationship matrix, complex traits 

---

## 🧠 一、研究背景

- 在复杂性状（如身高）遗传学研究中，用 GWAS 检出的 SNP 所解释的表型变异通常远小于家系 / 双胞胎研究估计的遗传率，这就是所谓的 “missing heritability” 问题。
- 传统 GWAS 依靠个别 SNP 的显著性检验，这使得那些效应很小但广泛存在的 SNP 難以达到显著阈值，因此可能被遗漏。作者希望探究：如果把所有常见 SNP 同时纳入模型，它们能否解释更多的遗传变异？ 
- 换句话说：剩余的 “missing heritability” 是否部分来源于许多效应很小、单独不显著的 SNP 而非某种完全不同的机制？
---

## 🔬 二、研究方法

| 模块 | 方法 / 策略 | 关键说明 |
|---|----------------|------------|
| 样本与 SNP 选取 | 使用 3,925 个互不相关个体，基因型数据为 294,831 个常见 SNP（genotyped SNP）| 这些 SNP 是 GWAS 中常用的常见变异集合 |
| 遗传关系矩阵 (Genetic Relationship Matrix, GRM) 构建 | 基于所有 SNP 估计样本间的基因型相似性 / 亲缘关系（G 矩阵） | G 矩阵用于捕捉个体间基因型协变关系 |
| 方差成分模型 / 线性混合模型 | 用混合线性模型将 SNP 的整体效应纳入模型，估计 SNP 所能解释的表型变异比例（即所有这些 SNP 的联合效应）| 该模型与经典 heritability 模型类似，但 SNP 效应是从基因型协方差矩阵推断 |
| 模拟验证 / 校正 | 通过模拟验证所估计方法的性能，并调整模型以校正基于 SNP 的关系估计误差 | 例如考虑 SNP–因果变异不完全连锁不平衡 (LD) 等影响 |
| 解释 / 假设检验 | 探讨为什么即使全部 SNP 一起估计，也不能完全解释遗传率；例如因果变异与被测 SNP 之间的 LD 不完全、潜在 rarer variant（低频 / 稀有变异）的作用等 | 这些讨论有助于理解“缺失遗传率”的可能来源 |

---

## 🧩 三、主要结果 / 结论

1. **常见 SNP 联合解释 ~45% 的身高变异**  
   当所有 294,831 个 SNP 联合纳入模型时，它们可以解释大约 45% 的身高表型方差。换言之，这些 SNP 共同起作用的效应能解释相当可观的一部分变异。
2. **“missing heritability”并非完全缺失**  
   作者认为，这部分未被单独显著 SNP 解释的变异，其实在整体模型中是存在的，只是每个 SNP 的效应太小，未能达到个体显著检验门槛。换句话说，这些效应“散落”在很多 SNP 上。
3. **LD 不完全 + 低频变异的作用**  
   作者还指出，即便纳入了大量常见 SNP，仍有一部分变异无法被解释，可能是因为：  
   - 因果变异与所测常见 SNP 之间的连锁不平衡 (LD) 不完全，导致测 SNP 无法完全捕获因果 SNP 的信号。  
   - 因果变异本身可能具有较低频率（低 MAF），而这些低频变异在常见 SNP 集合里难以代表。  
   这两点可能是解释剩余遗传率的关键因素。
4. **估计方法的校正 / 偏差讨论**  
   作者通过模拟和校正方法（如校正关系矩阵误差）表明，其估计并未严重偏倚，是比较稳健的。也指出即使用所有 SNP，仍然难以覆盖完全的遗传变异。
5. **对遗传结构 / 复杂性状架构的启示**  
   这项工作支持“高度多基因（polygenic）”模型的观点：复杂性状可能由非常多的 SNP（每个效应极小）共同作用。  
   同时强调，在寻求揭示剩余遗传率的时候，应兼顾稀有变异、测序变异、更密集标记和模型方法的改进。 

---

## 💬 四、个人理解与启发
- 这篇文章是遗传流行病学 “missing heritability” 问题研究中的经典之作，对理解 GWAS 信号解释力有限的根源提供了定量视角。  
- 在研究中，如果面对的性状也是高度多基因调控型（比如许多表型、疾病性状等），可以考虑采用类似的全 SNP 方差成分模型去估计解释能力，而不仅仅依赖显著 SNP。  
- 在设计基因型 / 表型关联研究时，要注意“稀有变异 + 连锁不完全”这一对潜在瓶颈，未来若有条件，应尽可能采集更高密度 / 全基因组测序数据来弥补。  

---

## 📚 五、参考引用
> Yang, J., Benyamin, B., McEvoy, B. P., Gordon, S., Henders, A. K., Nyholt, D. R., Madden, P. A., Heath, A. C., Martin, N. G., Montgomery, G. W., Goddard, M. E., & Visscher, P. M. (2010). *Common SNPs explain a large proportion of the heritability for human height*. *Nat Genet*, 42(7), 565–569. DOI: 10.1038/ng.608  

---

*最后更新：2025-10-17*
