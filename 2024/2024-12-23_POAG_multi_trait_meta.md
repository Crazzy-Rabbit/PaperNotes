### 📄 Large-scale multitrait genome-wide association analyses identify hundreds of glaucoma risk loci

**原文链接**: https://www.nature.com/articles/s41588-023-01428-5 \
**作者**: Xikun Han, Puya Gharahkhani, Andrew R. Hamel, et al. \
**期刊**: *Nat Genet*, 2023 \
**关键词**: glaucoma, multitrait GWAS, optic disc ratio, intraocular pressure, MTAG, genetic correlation, gene prioritization

---

## 🧠 一、研究背景

- 青光眼（glaucoma）是一种常见的、不可逆的视力损伤疾病，其发病机制复杂、遗传成分强。虽然已有多个 GWAS 研究鉴定出一些青光眼风险位点，但仍有大量遗传风险未被发现。
- 青光眼的表型与两个相关性状密切相关：**眼内压 (Intraocular Pressure, IOP)** 和 **视杯-视盘比 (vertical cup-to-disc ratio, VCDR)**。这些相关性状与青光眼共享部分遗传基础。
- 作者认为：通过 **多性状联合分析 (multitrait GWAS / MTAG)** 将青光眼与 IOP / VCDR 这类相关性状组合起来，一方面可提高统计检出率，另一方面有助于更准确识别那些特异于青光眼的遗传信号。
- 此外，作者还结合多种基因组学／post GWAS 分析策略（如 TWAS、gene prioritization，colocalization 等）来优先识别潜在功能基因。 

---

## 🔬 二、方法设计

| 模块 | 方法 / 策略 | 说明 / 关键点 |
|---|--------------------|-------------------------|
| **多性状联合 GWAS (MTAG / MultiTrait GWAS)** | 将青光眼 (POAG, primary open-angle glaucoma) 与 IOP 和 VCDR 这两个相关性状输入联合分析 | 提高检测功效，借助共享信号增强青光眼风险位点识别能力 |
| **独立位点鉴定 + Meta / 多祖源整合** | 在欧洲人群中鉴定青光眼相关联合位点（263 个 loci），然后在多祖源 Meta 分析中扩增至 312 个独立风险位点 | 在多个祖源中验证和扩展发现 |
| **校验 / 复制** | 使用 23andMe 独立队列进行复制检验（共 2.8M 样本量） | 许多位点在此独立验证队列中达标或达到显著性水平|
| **后 GWAS 功能注释 / 基因优先化** | - 利用 TWAS (基因表达关联) 方法（在视网膜 /眼组织表达背景下） <br> - Colocalization 分析 <br> - 多性状共定位 / 判别 SNP 是偏向 IOP / VCDR / 青光眼独特作用 <br> - 优先潜在可药物靶点基因 | 通过整合多种数据资源加强变异 → 基因 → 机制推断 |
| **遗传相关 / Mendelian Randomization 分析** | 估算青光眼与其他复杂性状 (如免疫疾病、多发性硬化症、红斑性狼疮等) 的遗传相关性和可能的因果方向 | 探索青光眼与全身性复杂性状之间的潜在联系 |

---

## 🧩 三、主要结果 / 结论

1. **大量新风险位点识别**  
   - 在欧洲族群中通过多性状联合分析鉴定出 **263 个** 独立青光眼相关位点。 
   - 通过多祖源 meta-analysis 扩充识别至 **312 个** 风险位点。大部分在 23andMe 验证队列中表现出一致效应（多数位点在阈值下复制或显著）
2. **共性 vs 特异性 SNP 分类**  
   - 作者将风险位点根据其在 IOP / VCDR 的信号强度 / colocalization 模型分类为三类：主要通过 IOP 调控、主要通过 VCDR、或更为青光眼特异的通路。此分类有助理解这些变异是如何作用于青光眼表型。
3. **功能注释与基因优先化**  
   - 通过 TWAS / 共定位 /多性状共定位策略优先若干基因作为潜在功能或药物作用目标。
   - 在这些优先基因中，有一些与视网膜 / 神经保护相关，有可能提供青光眼治疗的新方向。
4. **遗传相关性 / 因果分析**  
   - 文章报告多个性状（包括免疫相关疾病如多发性硬化症、系统性红斑狼疮等）与青光眼 / 相关表型具有显著遗传相关性。 
   - 使用 Mendelian Randomization 分析探索这些相关性方向，尽管部分结果受限于功率 / 可用变异。
5. **生物学 / 临床意义**  
   - 这些新识别的基因 / 通路可能为青光眼的发病机制（如神经保护、视网膜-神经连接、眼压调节等）提供线索。  
   - 研究中还提及已有某些药物（如糖尿病药物 Metformin）可能通过某些优先基因表现出潜在的保护作用（在新闻 /宣传中提及）。

---

## 💬 四、个人理解与启发

- 这篇文章展示了 **多性状联合 GWAS** 在复杂疾病（这里是青光眼）研究中的威力：通过借助相关性状 (IOP, VCDR) 的信号，极大地提升了检测青光眼本质关联变异的能力。  
- 在研究中，如果遇到某个性状有多个相关表型 / 亚表型（例如生化指标 + 影像学指标 + 表型量表等），可以考虑使用类似 MTAG / 多性状 GWAS 方法来增强发现能力。  
- 风险变异分类为 IOP / VCDR / 青光眼特异性的思路很有价值：可以帮助理解一个变异到底是通过哪条通路、哪个中介来影响终端表型。  
- TWAS / colocalization / 多性状共定位等在`GWAS meta`研究中几乎成为“标配”步骤。  
- 遗传相关性 + MR 分析则帮助连接青光眼与更广泛的疾病 /性状网络，是扩展研究方向的不二选择。 


---

## 📚 五、参考引用

> Han, X., Gharahkhani, P., Hamel, A. R., et al (2023). *Large-scale multitrait genome-wide association analyses identify hundreds of glaucoma risk loci*. *Nature Genetics*, 55(7): 1116–1125. DOI:10.1038/s41588-023-01428-5

---

*最后更新：2025-10-17*
