# cc 的投资工作流 - L1/L2/L3 Playbook

Source distilled from: `见创始人前的投研 Playbook（L1 _ L2 _ L3 ）.pdf`

## Universal Rules

- BP, media, and founder statements are claims, not verified facts.
- Separate output into facts, high-probability inference, and opinions/suggestions when ambiguity matters.
- Numbers must include source type: 文档披露, 公开报道, 创始人口述, or 我们推测.
- Each major section should follow: conclusion -> evidence -> uncertainty.
- If information is insufficient, state the gap and give the lowest-cost validation path.
- Default to a strong opposing view. Do not soften the critical attack just because the deal is promising.
- Preserve founder quotes with `>` blockquotes.
- Money style: USD, CNY, or 元. Do not use `$`.

## L1 - Pre-Meeting Notes

### Trigger

Use L1 when there is no first-hand founder-call transcript. Inputs may be BP, public materials, external notes, company name, interview, speech, or media coverage.

### Goal

Answer:

1. How should I introduce this founder/company before the meeting?
2. What should I ask in the meeting to force real information out?

L1 is not the place for a final investment judgment.

### File

Title: `{founder} / {company} - L1（YYYY-MM-DD）`

Path: `deals/{company}/pre-meeting-notes.md`

### Structure

```markdown
# {创始人姓名} / {公司名} - L1

## 1. 结论
## 2. 创始人模块
## 3. 一句话介绍
## 4. 解决方案与商业模式
## 5. 差异化与非共识
## 6. 现状与历程
## 7. 主要风险 / 反方观点

附录：原始材料原文
```

### Founder Module

This is the most important L1 section. Use three layers:

1. **成功经验与突出成绩**: past achievements, verified results, successful experiences related to the current project. Include at least three supported points.
2. **职业履历与背景**: education, work history in reverse chronological order, industry network, resources.
3. **过往失败与潜在风险点**: failures, lessons, personality/capability weaknesses, relevance to the current project.

Go down to product-level detail. Do not only write titles or company names.

Bad: `前 Nothing AI 负责人`

Good: `在 Nothing 负责过 Phone (2)、CMF Phone 1、手表、耳机、AI 按键等产品线`

### Company Module

One-sentence intro:

`{company} 通过 {solution} 为 {target users} 解决 {core need}，商业模式为 {brief model}.`

For solution and business model, distinguish verified facts from plans or unverified claims.

For differentiation and non-consensus, be concrete. Do not write generic "market is large" claims.

For current status, include users, revenue, funding, team size, and milestone timeline if available.

For risks, include at least three, ranked by severity. If L1 cannot verify them, say so.

### External Research

L1 must search beyond user-provided materials.

Founder sources: LinkedIn, X, YouTube speeches, Google/news, GitHub, Reddit.

Product reputation:

- App: App Store reviews, preferably with original quotes/screenshots.
- Non-app: X, Reddit, Product Hunt, Hacker News, community discussion.

Each external signal needs original quote and URL/source.

### L1 Question List

Principles:

- Questions should improve investment judgment, not just sound professional.
- Each question should validate a thesis, attack a weakness, expose evidence gaps, test founder clarity, or validate product/distribution/commercialization/moat.
- Ask for examples, real data, key decisions, abandoned paths, user behavior evidence, and failure cases.
- Ask less "how do you see the future"; ask more "what have you already observed".
- Avoid questions already answered by the material unless cross-checking.
- Include at least two 🔴 founder-least-wants-to-answer questions.

Format:

```markdown
### P0 | 这轮最该问的 5 个问题

### P1 | 方向选择（Why this / What opportunity / PMF 成立吗）

| 问题 | 验证目标 | Red flag | Green signal |
|---|---|---|---|

### P2 | 创始人认知深度（动机、深度思考、反直觉判断）

### P3 | 竞争优势（差异化与护城河）

### P4 | 🔴 创始人最不想回答的问题（至少 2 条）

### P5 | 其他模块（按需展开）
```

After L1, tell the user that any founder-call transcript can upgrade the workflow to L2, which rewrites the one-pager and question list from first-hand information.

## L2 - 投研初稿

### Trigger

Use L2 after receiving one first-hand founder-call transcript, regardless of length.

### Goal

Answer:

1. Which L1 assumptions were confirmed or overturned?
2. What is the real judgment after meeting the founder?
3. What still needs validation?

### Rewrite Rule

L2 is not an edit of L1. Archive L1 and rewrite one-pager and question list from scratch.

### File

Title: `{founder} / {company} - L2（YYYY-MM-DD）`

Path: `deals/{company}/full-report.md`

### Required Execution Order

1. Produce complete cleaned transcript and raw appendix.
2. Verify appendix completeness against original ASR.
3. Write analysis based on the appendix.
4. Assemble final document.

### Structure

```markdown
# {创始人姓名} / {公司名} - L2

一、Deal Intake + Founder One-Pager（重写版）
二、核心 Summary（主营业务与数据）
三、逐字稿清洗版（按话题分组，小标题用话题内容，不加序号前缀）
四、Diligence Question List（下次见面用）
五、✅ Review Checklist
六、🎯 访谈复盘
附录：原始对话（提问人加粗，一句不删，不按话题分组）
```

### Brief/Summary

L2 must open with a concise brief:

```markdown
> ## Brief
>
> **{company}** 是 {one-sentence intro with product, user, key data}.
>
> - **{key question 1}** {2-3 sentence answer with quote/data}
> - **{key question 2}** {2-3 sentence founder/team answer}
> - **{key question 3 optional}** {timing/competition/window}
>
> **为什么值得见？**
>
> 1. {reason}
> 2. {reason}
> 3. {reason}

**访谈人**：{interviewer} × {founder}
**时间**：{date} ｜ 时长约 {duration}
**人：X 分 | 事：X 分**
```

### Founder Analysis Style

Write like a profile, not a form.

Sections:

- 其人: career timeline, personality portrait, behavioral evidence, founder quotes, one-sentence summary.
- 核心商业逻辑: what they want to build, why this, why now, how they see competition.
- 深度思考: domain-specific questions that reveal judgment depth.
- 市场切入点: target market, user profile, founder insight, GTM.
- Special sections as needed: hardware, regulation, overseas, model choice, etc.

Rules:

- Use narrative paragraphs, not heavy tables.
- Quote founder heavily so the reader can feel their thinking style.
- Put 人/事 scores near the top.
- Fold competition, risk, and bear case into relevant sections; do not create generic standalone chapters for them.
- Use Chinese numerals for chapters. Do not use horizontal rules.

### Scoring

5-point scale, usually from 3.25 to 4:

- 4: 非投不可
- 3.75: 特别好
- 3.5+: 还不错，值得推荐继续深聊
- 3.5: 还不错，但亮点不够
- 3.5-: 比较一般
- 3.25: 特别差

Score 人 and 事 separately.

### Review Checklist

```markdown
## ✅ 投研 Review Checklist

### 材料完整性
- [ ] 创始人背景有独立来源验证
- [ ] 产品核心功能有实测或截图支撑
- [ ] 数据/traction 有明确出处
- [ ] 竞对分析覆盖主要玩家

### 逻辑一致性
- [ ] One-Pager 与原始材料无矛盾
- [ ] Question List 覆盖了所有证据缺口

### 判断质量
- [ ] 事实与推论已严格区分
- [ ] 反方观点已写入
- [ ] 下一步行动明确
- [ ] 是否还需要出 Investment Memo？（需要 -> 升级到 L3）
```

### Interview Retrospective

```markdown
## 🎯 访谈复盘

### ✅ 问得好的问题（3-5 个）
- **「原文问题」**
→ 好在：...

### ❌ 应该问但没问的问题（3-5 个）
- **应该问的问题**
→ 缺失原因：...
→ 建议下次怎么问：...

### 💡 访谈节奏观察（选填）
```

Before delivery:

- Check transcript completeness by sampling at least 10 dispersed keywords from the raw transcript and confirming coverage.
- Ensure at least four sections exist: One Pager, Summary, cleaned transcript, Question List.
- Tell the user which file is the formal version if temporary drafts were created.

## L3 - 投研完整文档

### Trigger

Use L3 when:

- There are at least two first-hand founder-call transcripts.
- External research/materials are available.
- The user is preparing IC or a final investment decision.

If fewer than two transcripts exist, ask for confirmation first.

### Structure

```markdown
# {创始人姓名} / {公司名} - L3

> **结论：{判断}。人 X 分，事 X 分。**

一、Deal Intake + Founder One-Pager（含壁垒四格评估）
二、核心 Summary（主营业务与数据）
三、逐字稿清洗版（按话题分组）
四、Evidence Map（含 Winner Pattern Study + 竞争对手全景图 + 抽样偏差评估）
五、Critical Storyline Attack
六、Diligence Question List
七、Sponsor 判断标准审视（如有内部 sponsor 偏好框架）
八、Investment Memo（含概率加权 Return Analysis）
九、✅ Review Checklist
十、🎯 访谈复盘
十一、Decision Log
附录：所有原始对话（提问人加粗，一句不删，不按话题分组）
```

### Evidence Map

Goal: cross-check multiple communications and external signals.

Use four categories:

- 印证: at least two independent sources support the same claim.
- 矛盾: different sources conflict.
- 无法验证: single-source claim without independent evidence.
- 外部调研补充: public materials, community discussion, product testing, or other independent signals.

Every item needs original quote and URL/source where applicable.

### Critical Storyline Attack

Structure:

```markdown
### 1. 最值得攻击的 3 个点
### 2. 每个点为什么致命
### 3. 可能的反驳是什么
### 4. 哪些证据可以真正缓解这些攻击
### 5. 最终判断
```

Pick at least three attack dimensions:

- Does the product have independent existence value?
- Is the need real or just demo demand?
- Is the product only a temporary wrapper around model capability?
- Would large model companies flatten the moat?
- Is distribution overestimated?
- Is retention supported by a real mechanism?
- Is workflow value sustainable?
- Is commercialization only theoretically valid?
- Is the founding team suited for this battle?

### Investment Memo + Decision Log

Include:

- 1-3 core judgments.
- Explicit uncertainties being accepted.
- Strongest bear case and why you still believe or do not.
- Future validation signals to track post-investment or before next meeting.

## Project Status Machine

After any pipeline run, ask the user to choose:

- 🔴 Stop: pause, no reminders.
- 🟡 Pending: observe; monthly reminder with materials, unresolved checklist gaps, and whether to continue.
- 🟢 Follow: actively follow; weekly reminder with existing materials, missing P0/P1 items, and request for updates.

## Same-Project Updates

Level upgrades:

- L1 -> L2 after first-hand transcript: archive L1, rewrite from scratch.
- L2 -> L3 after at least two transcripts plus external research: rewrite full document from all material.

Same-level updates:

1. Process new material.
2. Append raw material to appendix with timestamp.
3. Add `🔄 本次更新摘要`: what was added, what changed, which checklist gaps were answered.
4. Regenerate analysis from all material.

Never delete raw material. Never overwrite old raw material with a summary.

## One-Line Discipline

This playbook is not a template. It is three disciplines:

1. Do not treat narrative as fact.
2. Do not output generic questions.
3. Do not avoid the bear case.

If the Question List has no 🔴 founder-least-wants-to-answer questions, it is not qualified.
