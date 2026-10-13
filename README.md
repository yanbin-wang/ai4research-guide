# AI4Research：AI 自动化科学研究（自主科研）方向入门指南

> 面向新入学研究生整理的研究方向导读 · 更新于 2026-10
>
> 定位：**用 AI 自动化"科研流程本身"**（读文献 → 提假说 → 做实验 → 写论文 → 同行评审），而非用 AI 解决某个具体科学问题。

---

## 1. 方向的学术称呼（术语层）

| 层级 | 术语 | 说明 |
|---|---|---|
| 最大伞 | **AI for Science (AI4Science)** | 泛指 AI 加速一切科学领域（蛋白质、材料、气象……），口径太大，不宜作直接定位 |
| **方向级（主用）** | **AI for Research (AI4Research)** | 2025 年起接受度最高的方向级术语，见文末综述 [S1] |
| 系统级 | **Autonomous Scientific Research / Autonomous Scientific Discovery** | 强调端到端自主性，The AI Scientist、Co-Scientist 一线的标准描述 |
| 智能体视角 | **Scientific Research Agents / LLM-based Scientific Agents / Agentic Science** | 从多智能体架构切入的叫法 |
| 物理实验线 | **Self-driving Labs / Autonomous Experimentation** | 无人实验室（化学/材料领域已公认） |
| 写作/评审侧 | **Research Automation / Scientific Paper Generation** | 偏 NLP 社区（ACL/EMNLP）的叫法 |

开题写法建议：**"AI4Research / Autonomous Scientific Discovery with LLM-based Multi-Agent Systems"**，并在引言里与 AI4Science 划清边界：AI4Science 用 AI 解决科学问题本身，本方向用 AI 自动化科学研究的流程。

**检索关键词**：`AI4Research`、`autonomous scientific research`、`scientific discovery agents`、`AI scientist`、`research agents`、`self-driving laboratory`。

---

## 2. 领域全景：四大流派

| 流派 | 代表系统 | 干什么 |
|---|---|---|
| ① 端到端"AI 科学家" | The AI Scientist、AI Scientist-v2、Agent Laboratory、Kosmos、DeepScientist | 全流程自动化：假说→代码→实验→分析→成稿→模拟评审，单篇论文成本低至约 $15 |
| ② 假说生成 / 多智能体协作 | Google Co-Scientist、SciAgents | 不碰实验，专注"提出可验证的好假说"，多智能体互相批判、排序、进化 |
| ③ 物理实验闭环（无人实验室） | CMU Coscientist、Berkeley A-Lab、ChemAgents、FutureHouse Robin | LLM 编排实体机器人做化学/材料/生物实验，闭环"假说→合成→表征→迭代" |
| ④ 基础设施与评测 | FutureHouse 平台、PaperBench、Scientist-Bench、MLE-bench | 专职智能体 + 评测基准，划定 AI"科研能力"的边界 |

阶段叙事（"AI 在科研中的角色"）：**聪明助手 → 单任务执行者 → 流水线协调者**。目前主流系统处于 L2（人在环流水线自动化），L3 全自主是尚未达到的标杆。

---

## 3. 顶会论文清单（必读，均为主会/Findings 正式接收）

| 论文 | 会议 | 核心内容 | 链接 |
|---|---|---|---|
| **AI-Researcher: Autonomous Scientific Innovation**（港大 HKUDS 黄超团队） | **NeurIPS 2025 主会 Spotlight** | 全流程自主科研系统（文献→假说→实现→实验→成稿）+ Scientist-Bench 评测基准；开源 8k+ stars | [NeurIPS 正文](https://proceedings.neurips.cc/paper_files/paper/2025/hash/0d904d300a105809a2114d727851e759-Abstract-Conference.html) |
| **DeepScientist: Advancing Frontier-Pushing Scientific Findings Progressively** | **ICLR 2026** | 科学发现形式化为贝叶斯优化，月级时间尺度全自主；2 万+ GPU 小时，~5000 个想法、~1100 个实验验证，3 个前沿 AI 任务超过人类 SOTA | [arXiv:2509.26603](https://arxiv.org/abs/2509.26603) · [GitHub](https://github.com/ResearAI/DeepScientist) |
| **SAGA: Accelerating Scientific Discovery with Autonomous Goal-evolving Agents** | **ICLR 2026** | 双层架构：外层 LLM 自动设计/进化优化目标函数，内层做优化；覆盖药物发现、无机材料、纳米抗体等 | [ICLR 页面](https://iclr.cc/virtual/2026/10013687) |
| **SR-Scientist: Scientific Equation Discovery With Agentic AI** | **ICLR 2026** | LLM 自主写代码分析数据、发现科学方程（符号回归），比基线高 6–35%，并接入 RL 训练 | [arXiv:2510.11661](https://arxiv.org/abs/2510.11661) |
| **Agent Laboratory: Using LLM Agents as Research Assistants**（AMD + JHU） | **Findings of EMNLP 2025** | 三阶段（文献→实验→报告）半自主研究助手，成本比此前自主方法降 84% | [ACL Anthology](https://aclanthology.org/2025.findings-emnlp.320/) |

另有两个标志性节点：
- **The AI Scientist-v2** 生成的一篇论文达到了 **ICLR 2025 workshop** 的同行评审接收线（注意：仅 workshop，非主会）。
- **ScientistTwo**（Google Cloud AI Research，2026.09 arXiv）：在 107 个取自 ICLR/NeurIPS/ICML 录用论文的研究问题上声称 80.4% 改进人类 SOTA——但其主评估器在自家闭环内，held-out 独立评审下优势缩水到 0.1–0.2 分（σ≈0.7），**尚未进顶会，引用时注意口径**。

---

## 4. Nature / 期刊级代表作

| 论文 | 期刊·时间 | 核心内容 | 链接 |
|---|---|---|---|
| **Coscientist**（CMU, GPT-4 指挥化学机器人） | Nature · 2023.12 | 自主设计并执行钯催化交叉偶联实验，LLM 端到端驾驭实体实验室的标志性起点 | [doi:10.1038/s41586-023-06792-0](https://doi.org/10.1038/s41586-023-06792-0) |
| **A-Lab**（Berkeley） | Nature · 2023.4 | 无机材料闭环自主合成，41 天合成 41 种新材料 | [doi:10.1038/s41586-023-06734-w](https://doi.org/10.1038/s41586-023-06734-w) |
| **FunSearch**（DeepMind） | Nature · 2023.12 | LLM+进化搜索发现新数学构造（极值集合问题），"AI 做发现"的早期实证 | [doi:10.1038/s41586-023-06924-6](https://doi.org/10.1038/s41586-023-06924-6) |
| **The AI Scientist**（Sakana AI + UBC/Vector/Oxford） | Nature · 2026.3 | 首个全流程自动科学发现系统的正刊论文；v2 论文达 ICLR 2025 workshop 接收线 | 按标题检索 Nature 官网 |
| **Co-Scientist**（Google DeepMind，基于 Gemini） | Nature · 2026.5 | 多智能体假说生成 + 锦标赛进化；急性髓系白血病药物重定位获体外实验验证 | 按标题检索 Nature 官网 |
| **Robin**（FutureHouse） | Nature · 2026.5 | 生物医学发现循环；自主提出干性 AMD 新候选疗法（ripasudil、KL001） | 按标题检索 Nature 官网 |
| **ERA**（Google） | Nature · 2026 | LLM 引导树搜索生成专家级实证科研软件，数周工作缩至数小时 | [doi:10.1038/s41586-026-10658-6](https://doi.org/10.1038/s41586-026-10658-6) |
| **ChemAgents** | JACS · 2025.4 | 多智能体化学实验流水线：文献阅读/实验设计/计算执行/机器人操作四角色分工 | 按标题检索 JACS 官网 |
| **AlphaEvolve**（DeepMind） | 2025（技术报告） | 进化式 LLM 发现 4×4 复矩阵乘法新算法、优化 Google 数据中心调度——"AI 做研究"落到系统/芯片侧的实证 | 按标题检索 |

---

## 5. 综述（入门第一篇从这里开始）

| 编号 | 综述 | 说明 |
|---|---|---|
| [S1] | **AI4Research: A Survey of Artificial Intelligence for Scientific Research**（Chen et al., HIT/CSU/HKU 等） | 方向级权威综述，五任务分类：科学理解 / 学术综述 / 科学发现 / 学术写作 / 同行评审。arXiv:2507.01903 · [论文页](https://ai-4-research.github.io/) · [Awesome 论文列表](https://github.com/LightChen233/Awesome-AI4Research) |
| [S2] | **AutoResearch AI: Towards AI-Powered Research Automation for Scientific Discovery** | 提出 L1/L2-I/L2-P/L3 分层框架，把 2023–2026 主要系统逐一归类。[arXiv:2605.23204](https://arxiv.org/html/2605.23204) |
| [S3] | **AI 能否替代科学家**（华中科技大学等 16 机构，2026） | 五维评估框架（新颖性、可靠性等），梳理 2020–2026 系统演化史。[中文导读](https://www.techwalker.com/2026/0601/3188841.shtml) |
| [S4] | **The State of End-to-End AI Research Automation**（独立审计汇编，2026.07） | 逐条核对一手文献的可靠性审计，本文第 7 节数据多出于此。[链接](https://frankbueltge.de/e2e-automation) |

---

## 6. 评测基准

| 基准 | 出处 | 测什么 |
|---|---|---|
| **Scientist-Bench** | 随 AI-Researcher（NeurIPS 2025） | 自主科研系统的引导式创新 + 开放式探索任务 |
| **PaperBench**（OpenAI） | [arXiv:2504.01848](https://arxiv.org/abs/2504.01848) | 从零复现 20 篇 ICML 2024 Spotlight/Oral，8316 个可评分子任务；最强 agent 得分仅 21.0%，未超人类博士基线 |
| **MLE-bench** | arXiv:2410.07095 | 机器学习工程能力（Kaggle 式竞赛） |
| **CORE-Bench** | arXiv:2409.11363 | 计算可复现性 |
| **RE-Bench** | arXiv:2411.15114 | 前沿 AI R&D 能力，与人类专家对照 |
| **ResearchBench / AIRS-Bench / FIRE-Bench** | 2025–2026 | 科研任务粒度的能力边界测量 |
| **Stanford Agentic Reviewer** | Stanford ML Group | 独立（held-out）AI 评审器，可作第三方评估口径 |

---

## 7. 已知的失败模式与风险（独立审计，写论文前必读）

这些数字决定了这个方向"哪些坑不能再踩"，也决定了你的论文该把力气花在哪：

- **执行不可靠**：The AI Scientist 约 **42% 的实验因代码错误失败**；文献环节把 12 个已知概念全部判为"新颖"。
- **引用不可靠**：全领域 deep-research 系统引用准确率仅 **40–80%**；NeurIPS 2025 已录用论文中被发现 100 条编造引用。
- **诚实性问题**：给 7 个前沿 LLM 空数据集，**全部选择编造合成数据**而非承认不可行（完整性问题率 34.2%）。
- **验证不能自产自销**：LLM judge 即使有完整执行轨迹，准确率也 **<85%**；ScientistTwo 的教训——闭环内的 reviewer 打 91.9%，held-out 评审下优势仅 0.1 分。**验证必须放在独立于生成的层。**
- **可靠性分层规律**（Kosmos 审计，arXiv:2511.02824）：越机械锚定越可靠——数据分析 85.5% > 文献检索 82.1% > 综合解释 57.9%。
- **厂商自评风险**：Google Co-Scientist、AlphaEvolve 等的效果目前主要是厂商口径，缺独立第三方验证。

---

## 8. 建议的研究切入点

1. **"系统 + 独立评测"二件套是最稳的发表形态**（AI-Researcher/Scientist-Bench、DeepScientist 都是此配方）；纯做系统易被质疑自产自销式评估。
2. **选窄切口，别上来做"全能 AI 科学家"**：
   - 评审环节：AI peer review 的可靠性（验证独立性）
   - 假说评估 / 目标函数自动设计（SAGA 方向，刚起步）
   - 单阶段 agent：文献综述、复现、消融自动化
   - **Domain-specific research agent**：落到具体学科（如 AI+芯片 / EDA 场景），竞争比生物医学侧小
3. 阵地：NeurIPS / ICLR / ICML（+ 相关 workshop）、ACL/EMNLP（科研写作与文献智能体）、Nature 系（有实域验证时）。

---

## 9. 完整参考文献（BibTeX 友好格式）

```
[S1] Chen, Q. et al. "AI4Research: A Survey of Artificial Intelligence for Scientific Research." arXiv:2507.01903, 2025.
[S2] "AutoResearch AI: Towards AI-Powered Research Automation for Scientific Discovery." arXiv:2605.23204, 2026.
[S3] "Can AI Replace Scientists? A 2026 Answer from 16 Institutions." 华中科技大学等, 2026.
[S4] Bültge, F. "The State of End-to-End AI Research Automation." Independent audit, 2026-07.

[T1] Tang, J., Xia, L., Li, Z., Huang, C. "AI-Researcher: Autonomous Scientific Innovation." NeurIPS 2025 (Spotlight).
[T2] Weng, Y. et al. "DeepScientist: Advancing Frontier-Pushing Scientific Findings Progressively." ICLR 2026. arXiv:2509.26603.
[T3] Du, Y. et al. "Accelerating Scientific Discovery with Autonomous Goal-evolving Agents (SAGA)." ICLR 2026.
[T4] Xia, S., Sun, Y., Liu, P. "SR-Scientist: Scientific Equation Discovery With Agentic AI." ICLR 2026. arXiv:2510.11661.
[T5] Schmidgall, S. et al. "Agent Laboratory: Using LLM Agents as Research Assistants." Findings of EMNLP 2025.
[T6] Yamada, Y. et al. (Sakana AI) "The AI Scientist." Nature, 2026-03.
[T7] Gottweis, J. et al. (Google DeepMind) "AI Co-Scientist." Nature, 2026-05.
[T8] Ghareeb, E. et al. (FutureHouse) "Robin." Nature, 2026-05.
[T9] Aygün, E. et al. (Google) "An AI system to help scientists write expert-level empirical software (ERA)." Nature, 2026. doi:10.1038/s41586-026-10658-6.
[T10] Boiko, D. et al. (CMU) "Autonomous Chemical Research with Large Language Models (Coscientist)." Nature 624, 2023-12. doi:10.1038/s41586-023-06792-0.
[T11] Szymanski, N. et al. (Berkeley) "An Autonomous Laboratory for the Accelerated Synthesis of Novel Materials (A-Lab)." Nature 624, 2023. doi:10.1038/s41586-023-06734-w.
[T12] Romera-Paredes, B. et al. (DeepMind) "Mathematical Discoveries from Program Search with Large Language Models (FunSearch)." Nature 625, 2023. doi:10.1038/s41586-023-06924-6.
[T13] Ghafarollahi, A., Buehler, M. "SciAgents." JACS / arXiv, 2024.
[T14] Novikov, A. et al. (DeepMind) "AlphaEvolve." 2025.

[B1] Starace, G. et al. (OpenAI) "PaperBench: Evaluating AI's Ability to Replicate AI Research." arXiv:2504.01848, 2025.
[B2] "MLE-bench." arXiv:2410.07095.  [B3] "CORE-Bench." arXiv:2409.11363.  [B4] "RE-Bench." arXiv:2411.15114.
[B5] "Kosmos." arXiv:2511.02824 (含分层可靠性审计).
[B6] "ScientistTwo: Pioneering the Human Knowledge Frontier with Autonomous AI." Google Cloud AI Research, arXiv 2026-09.
```

---

*维护说明：本清单为课题组内部导读，数据与结论均标注一手来源；引用前请自行复核原文。*
