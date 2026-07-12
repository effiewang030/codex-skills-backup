---
name: fay-investment-comment
description: 模拟 Fay 视角的投资评论。基于 Fay 的历史判断记录和已识别偏好，模拟 Fay 对项目和创始人的投资评论。作为 pipeline 最后一站，在所有分析完成后自动运行。当用户说"模拟菲特的 comments"、"Fay 会怎么看"、"菲特会怎么说"、"跑一下 fay comment"时触发，或在 deal-intake pipeline 中作为最后一站自动调用。
---

# fay-investment-comment — Fay 投资评论模拟

## 用途

基于 Fay 的历史判断记录和已识别偏好（含月报提炼），模拟 Fay 对项目和创始人的投资评论。作为 pipeline 最后一站，在所有分析完成后自动运行，输出 Fay 视角的预判 comments。

## 触发方式

用户说"模拟菲特的 comments"、"Fay 会怎么看"、"菲特会怎么说"、"跑一下 fay comment"；或在 deal-intake pipeline 中作为最后一站自动调用（所有模式）。

## 前序文件检查

读取（至少需要 one-pager.md 才能运行）：
1. `deals/{公司名}/one-pager.md`（必须）
2. `deals/{公司名}/investment-memo.md`（如有）
3. `deals/{公司名}/attack.md`（如有）
4. `deals/{公司名}/evidence-map.md`（如有）
5. `skills/fay-investment-comment/references/fay-preferences.md`（偏好参考库）

## 偏好参考库

读取 `references/fay-preferences.md`，获取：
- Fay 的判断维度
- 加分 / 减分清单
- 历史案例
- 月报原话

## 八维度预判

| 维度 | 权重 | 说明 |
|------|------|------|
| **产品 Sharpness** | ⚡ 最高 | 产品是否足够犀利、有独特切入点 |
| **Bottom-up vs Top-down** | 高 | 创业路径判断 |
| **创业 Pattern & 人事匹配** | 高 | 创始人是否适配这件事 |
| **战略选择的 Disruptiveness** | 中 | 选择是否有颠覆性 |
| **壁垒真实性** | 中 | Pricing power / compounding |
| **胜率 × 赔率** | 中 | 风险回报比 |
| **竞争格局** | 中 | 是否对竞争格局有深入研究 |
| **Meaningful Stake** | 低 | 是否值得持有有意义的股份 |

**判断阈值**：
- 维度 1-3 中有两个以上减分 → Fay 大概率不推进
- 维度 7（竞争格局）没做过研究 → 准备不充分

## 风格要求

- 直接犀利，用具体细节说话
- 有结构但不学术
- 敢下判断
- 在合适位置引用 Fay 月报原话（如壁垒 = pricing power、compounding 思维、meaningful stake 等）
- 类比历史案例（从判断记录中找最相似的 1-2 个案例）

## 输出物

`fay-comment.md`，包含：
- 八维度预判表（表格形式）
- 模拟 Fay Comments（直接犀利风格）
- 预判结论
- 历史案例类比（1-2 个）
- 免责声明：**模拟预判不代表 Fay 实际判断**

**Redoc 上传**（模式 A/B）：自动上传为母文档下的独立子文档，标题固定为 `Fay's Potential Comments`

## 核心约束

- 不发明内容，不把 narrative 当事实
- 不编造 Fay 未表达过的偏好维度，只使用已记录的判断逻辑和月报原话
- 模拟 Fay 的说话风格，不写成学术分析
- 不给出超出材料支撑的判断
- 每次输出必须附免责声明

## 偏好库更新

每次有新的 L3 项目 Fay 反馈时，更新 `references/fay-preferences.md` 并同步 Redoc 源文档。

## 与其他 Skill 配合

- Pipeline 位置：investment-memo 之后、汇总 full-report.md 之前（最后一站）
- 输出写入 full-report.md 的 "06 Fay Comments 模拟" 章节
- 所有模式（A/B/C）都运行——只要有 one-pager 就能跑
