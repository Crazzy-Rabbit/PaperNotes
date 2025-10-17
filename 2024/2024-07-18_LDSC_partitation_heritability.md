### 📄  Partitioning heritability by functional annotation using genome-wide association summary statistics

**原文链接**: https://www.nature.com/articles/ng.3404 （DOI: 10.1038/ng.3404） \
**作者**: Hilary K. Finucane, Brendan Bulik-Sullivan, Alexander Gusev, et al. \
**期刊**: *Nat Genet*, 2015 \
**关键词**: stratified LD score regression, heritability partitioning, functional annotation

---

## 🧠 一、研究背景

- 在很多复杂性状 / 疾病的 GWAS 研究中，人们注意到某些功能类别（如增强子、保守区、染色体修饰区域等）的 SNP 往往贡献的遗传率比其在整个基因组中所占比例要大，也就是说存在 **遗传力的功能富集**。
- 但要准确量化这种富集，需要考虑 SNP 之间的连锁不平衡 (LD)，否则易混淆真实富集信号与 LD 污染。  
- 传统的方法要么难以扩展，要么不能很好地校正 LD 影响。本研究提出了一种新的 **分层 LD Score 回归 (stratified LD score regression, S-LDSC)** 方法，能够在 summary statistics 层面估计各功能类别对总遗传率的贡献，同时考虑 LD 结构的影响。
- 这样就能回答：在不同功能注释或细胞类型注释下，哪些 SNP 类别在遗传率中被“放大”或“富集”？  

---

## ⚙️ 二、方法原理（核心逻辑）
### 📏 1. LD Score 回归 回顾

- 经典 LD Score 回归假设对于每个 SNP $j$，其检验统计量（如 $\chi_j^2$）的期望值可以线性表示为：
  <p align="center">
    <img src="https://latex.codecogs.com/svg.latex?\displaystyle\mathbb{E}[\chi_j^2] = 1 + \frac{N \, h^2}{M} \, \mathrm{LDScore}(j) + \text{confounding}">
  </p>

  其中 $\mathrm{LDScore}(j)$ 是 SNP $j$ 与周围 SNP 的 LD 相关性累加值。  
- 这个模型帮助区分检验统计量膨胀的来源（多基因信号 vs 混杂偏倚）——见 Bulik-Sullivan 等人的 LD Score regression 方法。  

### 🧩 2. 分层 LD Score 回归（S-LDSC）

在经典模型基础上，S-LDSC 扩展到多个注释类别（functional categories）：

#### (1) 注释类别定义与注释矩阵构建

- 将基因组上的 SNP 分入多个注释类别（annotations），例如是否属于保守基因区域、增强子、染色质标记、H3K4me3 区域等。
- 构建注释矩阵 $A_{j,k}$，其中对于 SNP $j$，在注释类别 $k$ 下是否被标注（可为 0/1 或加权注释）。

#### (2) 模型假设与回归表达式

- 假设每个 SNP 的效应方差可分解为多个注释类别的加权和：
  <p align="center">
    <img src="https://latex.codecogs.com/svg.latex?\displaystyle\mathrm{Var}(\beta_j) = \sum_k \tau_k A_{j,k}">
  </p>  

  其中 $\tau_k$ 是注释类别 $k$ 的效应方差参数。  
- 则期望 $\chi^2$ 值可写成对注释加权的线性组合：
  <p align="center">
    <img src="https://latex.codecogs.com/svg.latex?\displaystyle\mathbb{E}[\chi_j^2] = 1 + \sum_k \tau_k \, \mathrm{LDScore}_{j,k}">
  </p>  

  这里的 $\mathrm{LDScore}_{j,k}$ 是 **类别特异性 LD Score**，即考虑注释类别 $k$ 的 LD Score（SNP 与类别 $k$ 注释 SNP 的 LD 累加度量）。  
- 用加权回归对 $\chi_j^2$ 对各 $\mathrm{LDScore}_{j,k}$ 回归，即可估计各 $\tau_k$，由此推断出每个注释类别对总遗传率的贡献。

#### (3) 偏倚 / 校正 & 标准误估计

- 在回归中，需要考虑异方差 (heteroskedasticity) 和 SNP 相关性（因为 SNP 之间并非独立）。论文中使用 **加权最小二乘** 和 **block jackknife** 方法来估计标准误并控制相关性。
- intercept 项仍然可以捕获残余偏倚 / 混杂效果。

---

## 📊 三、数据与实验设计

| 模块 | 描述 |
|---|---|
| **GWAS summary 数据** | 选择了 17 个复杂性状 / 疾病，平均样本量约为 73,599 人次 |
| **注释集合** | 包括常见注释类别（如保守区域、增强子、染色体修饰区域、细胞类型特定注释等） |
| **模拟分析** | 构造无富集 / 有富集 / 模型错配 (misspecification) 等情境，检验方法的校准性与选择能力 |
| **真实富集推断** | 在真实 GWAS 中对各注释类别做富集估计，并检验细胞类型特异注释在不同性状中的富集程度 |



## 🧩 四、主要结果 / 结论

1. **保守区域 (conserved regions) 的遗传率富集普遍存在**  
   对多种性状而言，保守基因组区域通常在遗传率中占比被显著富集（即其贡献 > 相对于 SNP 所占比率）。
2. **免疫相关疾病在 FANTOM5 增强子 (enhancers) 上遗传率富集显著**  
   特别是在炎症 / 免疫性疾病中，这类增强子注释表现出强烈富集。
3. **细胞类型 / 组织特异注释的富集**  
   在某些性状中，与中枢神经系统 (CNS) 相关的细胞注释（如大脑增强子）在 BMI、教育年限、吸烟行为等性状中也表现显著富集。
4. **方法稳定性与对比**  
   模拟结果表明，S-LDSC 在多种情境下校准良好，能在复杂 LD 结构下稳定估计富集系数。  
   与其他方法相比，S-LDSC 在处理大型 GWAS summary 数据时具有可扩展性和稳健性优势。


---

## 💬 五、个人理解与启发

- 这篇论文开创性地把 **功能注释 + GWAS summary statistics** 融合在一个回归框架中，是后来许多遗传率富集 / 注释方法（如 LDSC-SEG、S-LDSC 扩展版、Cell-type enrichment） 的基石。  
- 在研究中：
  - 可以用 S-LDSC 来检查 GWAS 结果中哪些注释类别（如 enhancer、TF binding site、保守区等）真的具有富集性；  
  - 在做细胞类型 / 组织特异注释富集之前，用 S-LDSC 校正 LD 是一个标准步骤；  
  - 若以后做单细胞 / 空间转录组 + GWAS 整合，也可以借鉴这种“注释 + 分层 LD Score”思想，将空间 / 细胞注释纳入模型进行遗传率分区；
  - 此方法也帮助判断某些注释是否有意义：如果某个注释类别估计出的富集系数很低或不显著，可能该类别对该性状贡献有限。

---

## 📚 六、参考引用

> Finucane, H. K., Bulik-Sullivan, B., Gusev, A., et al (2015). *Partitioning heritability by functional annotation using genome-wide association summary statistics*. *Nature Genetics*, 47(11), 1228–1235. DOI: 10.1038/ng.3404

---

*最后更新：2025-10-17*
