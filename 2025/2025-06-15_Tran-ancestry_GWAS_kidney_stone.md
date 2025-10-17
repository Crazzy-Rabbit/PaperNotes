### 📄 Trans-ancestry GWAS identifies 59 loci and improves risk prediction and fine-mapping for kidney stone disease
**原文链接**: https://www.nature.com/articles/s41467-025-58782-7 （DOI: 10.1038/s41467-025-58782-7） \
**作者**: Xi Cao, Minghui Jiang, Yunlong Guan, et al.  \
**期刊**: *Nat Commun*, 2025 \
**关键词**: GWAS, population stratification, mixed models, ancestry correction, cryptic relatedness  

---

## 🧠 一、研究背景

- 肾结石疾病（Kidney Stone Disease, KSD）是一个复杂、多因素驱动的疾病，受遗传、代谢、环境等多种因素影响。
- 虽然已有若干 GWAS 探索 KSD 的风险变异，但多数研究限于单一祖源人群，这可能限制发现变异的跨人群通用性与效果。
- 跨祖源 GWAS（trans-ancestry GWAS）能够利用不同人群的 LD 结构差异，提高检测功率、改善信号定位与细化变异识别。  
- 此外，通过更精确的 fine-mapping 驱动因果变异识别，以及构建跨人群有效的 polygenic risk score (PRS) 模型，是本研究的主要目标之一。

---

## 🔬 二、研究方法（综述中讨论的方法）

| 模块 | 方法 / 策略 | 说明 / 关键点 |
|---|-------------------------|-----------------------------|
| **跨祖源 Meta-分析 (Trans-ancestry GWAS meta-analysis)** | 将欧洲 (EUR) 与东亚 (EAS) 人群的 GWAS 数据合并做 meta 分析 | 样本量：31,715 例 + 943,655 对照（EUR + EAS）|
| **显著位点鉴定** | 在 meta 分析结果中识别显著风险位点（P < 5×10⁻⁸），共得到 59 个独立位点，其中 13 个为新发现 | 这些位点在 EUR 和 EAS 人群中的效应方向一致性较高 |
| **Fine-mapping / 因果信号定位** | 在每个风险位点做精细定位 (credible set / posterior inclusion probability, PIP) 分析 | 共检测到 1,612 个候选变异，并在其中定位出 25 个具有 PIP > 0.5 的因果信号 |
| **优先基因识别 / 生物注释** | 在新位点中指出 TRIOBP 基因作为一个可能关联基因（在某些位点） | 作者对 TRIOBP 基因及其可能的生物学机制做了讨论 |
| **跨人群 PRS 构建与评估** | 使用 PRS-CSx（跨人群 PRS 方法）构建 EAS + EUR 的联合 PRS 模型 | 该模型优于其他 PRS 构建方法，在不同人群中预测性能更佳 |
| **风险分层 / 效果估计** | 将样本按 PRS 分位数分组，比较最低与最高组的 KSD 风险比 (odds ratios) | 相对于中间三分位组，最低组 OR ~0.57，最高组 OR ~1.83 等 |
| **年龄发病 / 表型关联分析** | 检验高 PRS 人群是否有更早发病倾向等 | 结果表明：较高 PRS 的患者发病年龄可能更年轻 |

---

## 🧩 三、主要发现

1. **识别 59 个肾结石关联位点**  
   包括 13 个此前未报道的新位点，且大多数在 EUR 和 EAS 中效应方向一致。 
2. **Fine-mapping 定位到 25 个高置信因果信号**  
   在多个风险位点中成功将候选变异缩减到较小 credible set，并识别出 PIP > 0.5 的因果候选。
3. **优先基因 TRIOBP**  
   在一个新位点中，作者优先将 TRIOBP 作为可能的致病基因之一，结合其生物学背景进行推测。
4. **跨人群 PRS 表现提升**  
   使用 PRS-CSx（结合 EAS + EUR 数据）构建的联合 PRS 在预测效果上优于单一人群构建的模型。
5. **风险分位数差异强烈**  
   相比于中间组，最低 PRS 组与最高组在 KSD 风险上有显著差异（OR 约 0.57 vs 1.83）
6. **发病年龄关联**  
   较高 PRS 的 KSD 患者倾向于较早发病，这提示 PRS 在疾病进展 /预后层面可能也有意义。

---

## 💬 四、个人理解与启发
- 这篇研究是跨祖源 GWAS 在具体疾病应用上的典范：不仅进行了 meta 分析，还把 fine-mapping、跨人群 PRS、风险建模都整合进来。  
- 对做类似项目的启发包括：  
  - 如果有多个人群的 GWAS 数据，可以尝试跨祖源 meta 分析以提高功效与通用性；  
  - 在识别信号之后做 fine-mapping 是关键，对因果变异定位帮助很大；  
  - 构建跨人群 PRS（如 PRS-CSx 或其他整合方法）比单一 PRS 更稳定 / 更有推广性；  
  - 在风险分层 / 发病年龄 /预测模型层面评估 PRS 的临床意义是很有价值的附加分析；  
  - 在优先基因层面，可以结合多组学注释（如 eQTL、表观注释）对候选基因做加权注释。

---

## 📚 五、参考引用
> Cao, X., Jiang, M., Guan, Y., et al (2025). *Trans-ancestry GWAS identifies 59 loci and improves risk prediction and fine-mapping for kidney stone disease.* *Nature Communications*, 16, 3473. DOI: 10.1038/s41467-025-58782-7
---

*最后更新：2025-10-17*
