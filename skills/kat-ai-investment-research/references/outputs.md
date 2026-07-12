# Output Structures

Use this reference when creating files or final reports.

## Local Files

Prefer this structure when the user wants persistent deal files:

```text
deals/{company-name}/
  full-report.md
  investment-summary-for-delivery.md
  intake-card.md
  one-pager.md
  evidence-map.md
  attack.md
  question-list.md
  investment-memo.md
  fay-comment.md
  meta.json
```

Use only the files needed for the requested task. For one-off chat answers, produce the answer inline unless files are clearly useful.

## full-report.md Order

Use this order for full pipeline reports:

```markdown
# {Company} 投研全档 · {YYYY-MM-DD}

## AI 摘要
## 逐字稿 / 材料原文
## 投研 Review Checklist
## 01 Deal Intake
## 02 Investment One-Pager
## 03 Evidence Map
## 04 Critical Storyline Attack
## 05 Diligence Question List
## 06 Investment Memo
## 07 Fay Comments 模拟
## 访谈复盘
---
## 材料附录
```

For Mode B or C, omit sections that were intentionally not run and add a short note explaining why.

## Delivery Documents

Mode A:
- `investment-summary-for-delivery.md`.
- Contents: one-pager plus cleaned transcript.
- Intended title if publishing: `{Company}-投研初稿-{YYYYMMDD}`.

Mode B or C:
- `one-pager.md`.
- Intended title if publishing: `{Company}-one pager`.

Fay comments:
- `fay-comment.md`.
- Intended title if publishing: `Fay's Potential Comments`.

## Review Checklist

Include this checklist in full reports:

```markdown
## 投研 Review Checklist

- [ ] 公司定位是否清楚，且没有把愿景写成事实。
- [ ] 创始团队信息是否有来源，关键信息缺失是否标注。
- [ ] 产品能力是否基于材料、截图、demo、用户反馈或公开资料。
- [ ] 竞品和替代方案是否列出，且不是只复述公司说法。
- [ ] 融资、估值、收入、用户数等数字是否标注来源。
- [ ] 核心 claim 是否区分独立证据、同源复述和未验证。
- [ ] 最大 bear case 是否具体、有杀伤力。
- [ ] 下一轮问题是否能验证关键假设。
- [ ] 结论是否明确为 Recommend / Pending / Pass / Insufficient Info。
```

## Source Labels

Use these labels consistently:
- 【文档披露】
- 【公开报道】
- 【创始人口述】
- 【我们推测】
- 【未核实】

## Redoc Safety

If publishing to Redoc or another document system:
- Create a blank parent document named after the project when needed.
- Add only agent-created child documents.
- Never modify, delete, or move manually added user documents.
- Return the published link when available.
