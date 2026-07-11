---
name: cc-investment-workflow
description: Use when the user asks to run "cc 的投资工作流", "cc 投资工作流", or a L1/L2/L3 founder-meeting investment workflow. Also use for pre-founder-meeting investment prep, founder one-pagers, high-information question lists, post-founder-call analysis, founder profile writeups, evidence maps, critical storyline attacks, investment memos, IC preparation, or deal status tracking. This skill is especially relevant when inputs include BP decks, company names, public materials, founder-call transcripts, external research, or repeated deal updates.
---

# cc 的投资工作流

## Core Idea

This workflow turns limited deal material into increasingly grounded investment judgment across three levels:

- **L1 Pre-meeting Notes**: before meeting the founder; use BP, public materials, media, company name, or external notes. Output a founder/company one-pager and a sharp question list.
- **L2 投研初稿**: after one founder call transcript. Rewrite from scratch using first-hand information. Output a narrative founder analysis, cleaned transcript, next-meeting question list, review checklist, and interview retrospective.
- **L3 投研完整文档**: for IC or final decision, usually after at least two founder-call transcripts plus external research. Output full memo, evidence map, critical attack, diligence questions, decision log, and status.

Never treat BP or founder narrative as fact. Separate facts, high-probability inference, and opinions. Numbers must state source type: document disclosure, public report, founder statement, or analyst estimate.

## Routing

Use the smallest level that matches the available material:

- No first-hand founder transcript -> **L1**.
- One first-hand founder transcript, any length -> **L2**.
- At least two first-hand transcripts plus external research, or user is preparing IC/final decision -> **L3**.

If the user asks for L3 with fewer than two transcripts, say the current material is below the normal L3 threshold and ask for confirmation before proceeding.

Each level is a rewrite, not an incremental patch:

- L1 is archived when L2 begins.
- L2 is rewritten when L3 begins.
- Same-level updates append raw material, add a "本次更新摘要", then regenerate analysis from all material.

Read `references/l1-l2-l3-playbook.md` before producing a cc workflow deliverable.

## Non-Negotiables

- Do not invent facts. Missing evidence must be explicit.
- Use founder quotes as blockquotes and do not rewrite their meaning.
- Question lists must include at least two red-flag/attack questions the founder may least want to answer.
- Prefer specific, evidence-seeking questions over broad narrative prompts.
- In every section, lead with the judgment, then evidence, then uncertainty.
- Use USD for dollars and CNY or 元 for RMB.
- Do not overuse tables in L2; L2 should read like a profile/narrative, not a form.

## Output Defaults

Use local deal folders when files are involved:

`deals/{company-name}/`

Default filenames:

- L1: `pre-meeting-notes.md`
- L2/L3: `full-report.md`

After a pipeline run, ask the user to choose deal status:

- 🔴 Stop: pause, no reminders.
- 🟡 Pending: observe, monthly reminder.
- 🟢 Follow: active follow-up, weekly reminder.
