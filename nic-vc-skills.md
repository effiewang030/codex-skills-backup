# nic-vc-skills

更新时间：2026-07-13

这份文档是 7 个 VC / AI 投研相关 Codex skills 的总索引与使用说明。原始 skill 已安装到本机 Codex skills 目录，可在后续任务中按触发场景调用。

## 已安装 skills

| Skill | 核心用途 | 典型触发 |
|---|---|---|
| `vc-meeting-notes` | VC 会议转写清洗与 IC 会议纪要 | 录音转写、Recall 文本、创始人会议纪要、IC 材料 |
| `vc-voice-mining` | 投资人公开发声与投资哲学深挖 | 挖某个投资人的观点、quotes、podcast、blog、philosophy |
| `pr-filter` | 媒体稿件 PR 属性识别与有效信息萃取 | 这篇报道可信吗、是不是 PR、哪些信息可用 |
| `hightech-researcher-mining` | 深科技研究者/技术领袖调研 | 教授/CTO/PhD 背景、研究图谱、会议问题、red flags |
| `hype-check` | 热赛道退烧诊断与本质判断 | 赛道是不是泡沫、需求真伪、readiness、该不该投 |
| `deal-intake` | 一级市场投研材料主 pipeline | BP 拆解、one pager、L1/L2/L3 投研初稿、上会材料 |
| `ai-infra-learner` | AI infra 技术学习、成本、层级与护城河分析 | DeepSeek/MoE/推理成本/stack 定层/PhD 会前准备 |

## 总体使用逻辑

这些 skills 可以组成一条完整的 AI/VC 投研工作流：

1. **收到项目或材料**
   - 用 `deal-intake` 判断走 L1 / L2 / L3。
   - 如果是媒体报道，先用 `pr-filter` 做 PR 指纹和信息分层。
   - 如果有创始人会议录音或转写，用 `vc-meeting-notes` 清洗或生成纪要。

2. **判断赛道与公司本质**
   - 赛道热、大家都在看时，用 `hype-check` 做退烧诊断。
   - 单家公司处于热赛道中，用 `hype-check` Mode B 做本质检验。
   - AI infra 公司或技术型项目，用 `ai-infra-learner` 做 stack 定层、成本和替代风险。

3. **准备人和会议**
   - 见投资人或研究某个 VC，用 `vc-voice-mining` 挖公开思想与 key quotes。
   - 见研究者、教授、技术创始人，用 `hightech-researcher-mining` 做研究图谱、合作者网络和问题清单。
   - 见 AI infra / agent / RL / GUI agent 研究者，用 `ai-infra-learner` Mode E 准备技术问题。

4. **形成上会材料**
   - 用 `deal-intake` 汇总成可追溯、敢质疑的投研初稿。
   - 证据不足处必须标注缺口与最低成本验证路径。
   - 所有关键判断区分：【事实】、【高概率推论】、【观点/建议】、【BP claim】。

## Skill 速记

### vc-meeting-notes

两种模式：

- **Mode A：半精转写**  
  将 Recall / Otter / 飞书妙记等原始转写清洗为可读文本。核心原则是“清洗，不摘要”：保留实质信息、说话人口语特征、个性信号和时间戳。

- **Mode B：IC 会议纪要**  
  将转写或笔记重组为内部投资备忘录，输出公司概要、赛道、团队、产品、财务、融资、风险、后续问题等结构化内容。

重要规则：

- 不要发明会中没出现的数据。
- 数字、日期、人名、公司名、融资金额必须保留。
- 如有 BP 或 pre-meeting brief，要标注“与会前理解一致 / 有更新或修正”。

### vc-voice-mining

用途：系统性挖掘投资人的深度思想。

搜索层级包括：

- 自有 podcast / blog / substack
- 基金官方 blog / reports / LP letters
- VC podcast
- 科技媒体、金融媒体
- 行业大会与大学演讲
- 第三方评价，如 Midas、PreQin、Cambridge Associates
- 社交媒体

提取标准：

- 深度 > 广度。
- 优先提取投资哲学、反直觉判断、AI 方向预判、创始人筛选标准、失败教训、决策框架。
- 避免泛泛 PR 话术和没有论据的预测。

### pr-filter

三种模式：

- **Mode A：单篇 PR 指纹分析**
- **Mode B：多篇交叉验证**
- **Mode C：信源可信度评级**

核心评分：

- 8 个维度，每维 0-2 分，总分 0-16。
- 维度包括来源渠道、信源结构、叙事语气、数据透明度、时间绑定、结构格式、竞品语境、作者署名。

信息分层：

- 硬数据：可直接使用，但仍标注可验证性。
- 可查证声明：列验证路径。
- 不可查证声明：仅参考。
- 纯 PR 话术：过滤。

最重要动作：反向阅读，分析稿子“没说什么”。

### hightech-researcher-mining

面向具身智能、量子计算、脑机接口等前沿深科技领域的研究者/技术领袖。

完整输出包括：

- 研究图谱
- 最值得问的问题
- 人物还原
- 合作关系密度分析
- 叙事演变时间线
- 研究定位
- Red Flags
- 深度思想提取

搜索重点：

- Google Scholar / arXiv / 顶会 / 顶刊
- 实验室与公司官网
- 技术博客、GitHub、公开演讲
- 技术 podcast、行业大会、专利
- 合作者、学术谱系、学生去向
- 争议、可复现性、利益冲突、承诺与交付 gap

### hype-check

核心问题不是“谁在做”，而是“该不该做”。

四种模式：

- **Mode A：退烧诊断**  
  判断热赛道的热度来源、数的可持续性、需求真伪、技术与行业 readiness、资本游戏。

- **Mode B：单公司本质检验**  
  在热门叙事下反向检查一家公司到底在赌什么，数是否真实，壁垒是否成立。

- **Mode C：冷赛道 readiness 判断**  
  判断一个没热起来的方向是否到了进场时刻。

- **Mode D：科学驱动型赛道前景判断**  
  用于医疗、AI4S、材料、能源等方向，重点看科学验证阶段、支付方逻辑、产业化路径、中外差异。

核心方法：

- 反事实分析
- 幸存者偏差纠正
- 基率分析
- 自然实验 / DID
- 选择性暴露检查
- 均值回归
- 委托代理分析
- 社会证明与信息级联
- 锚定效应检测

### deal-intake

一级市场投研初稿主 pipeline。

第一步永远先判断 L1 / L2 / L3：

- **L1：Pre-meeting Notes**  
  有 BP、外部资料、公司名，但没有自己的访谈逐字稿。输出见面前材料和问题清单。

- **L2：投研初稿**  
  拿到自己的访谈逐字稿后，从零重写 full report。必须先整理逐字稿，不在 L1 上增量更新。

- **L3：投研完整文档**  
  有 2 次以上自己的访谈逐字稿，并补充外部研究。加入 Evidence Map、Critical Storyline Attack、Investment Memo、Decision Log。

核心约束：

- 不发明内容。
- 不把 BP 或创始人口述当事实。
- 关键结论必须区分事实、推论、观点、BP claim。
- 默认给反方视角，主动找致命伤。

### ai-infra-learner

帮助 VC 投资人建立 AI infra 技术直觉。

五种模式：

- **Mode A：架构拆解**  
  解释 DeepSeek、MoE、Flash Attention、分布式训练等系统如何工作。

- **Mode B：成本与价格情报**  
  估算训练成本、推理成本、GPU 经济学、API 价格。

- **Mode C：层级与护城河分析**  
  判断公司处于 AI stack 哪一层，以及被模型厂商、开源、云厂商、硬件厂商替代的风险。

- **Mode D：前沿动态追踪**  
  追踪最新论文、benchmark、推理优化、硬件和成本下降。

- **Mode E：深度研究者对话准备**  
  针对 PhD、教授、AI infra / agent 研究者，生成基于论文细节的问题清单。

AI stack 五层：

- Layer 5：应用层
- Layer 4：应用基础设施层
- Layer 3：推理优化层
- Layer 2：训练基础设施层
- Layer 1：硬件与系统层

直觉：

- 越靠近硬件，壁垒越高。
- 越靠近应用，市场越大但壁垒越低。
- Layer 4 最脆弱，要特别检查是否会被模型原生化。

## 推荐组合

| 场景 | 推荐组合 |
|---|---|
| 收到 BP，准备第一次见创始人 | `deal-intake` L1 + `pr-filter` + `hype-check` Mode A |
| 见完创始人，有转写稿 | `vc-meeting-notes` Mode A/B + `deal-intake` L2 |
| 热赛道里看单家公司 | `hype-check` Mode B + `deal-intake` + `pr-filter` |
| AI infra 公司判断壁垒 | `ai-infra-learner` Mode C + Mode B + `hype-check` Mode B |
| 见教授/技术创始人 | `hightech-researcher-mining` + `ai-infra-learner` Mode E |
| 研究某个投资人 | `vc-voice-mining` |
| 科学驱动方向，如 AI4S / 医疗 / 材料 | `hype-check` Mode D + `hightech-researcher-mining` |

## 本地安装位置

```text
/Users/wangjiayue/.codex/skills/vc-meeting-notes
/Users/wangjiayue/.codex/skills/vc-voice-mining
/Users/wangjiayue/.codex/skills/pr-filter
/Users/wangjiayue/.codex/skills/hightech-researcher-mining
/Users/wangjiayue/.codex/skills/hype-check
/Users/wangjiayue/.codex/skills/deal-intake
/Users/wangjiayue/.codex/skills/ai-infra-learner
```

## 原始文件来源

```text
/Users/wangjiayue/Desktop/vc-meeting-notes.skill
/Users/wangjiayue/Desktop/vc-voice-mining.skill
/Users/wangjiayue/Desktop/pr-filter.skill
/Users/wangjiayue/Desktop/hightech-researcher-mining.skill
/Users/wangjiayue/Desktop/hype-check.skill
/Users/wangjiayue/Desktop/deal-intake.skill
/Users/wangjiayue/Desktop/ai-infra-learner.skill
```
