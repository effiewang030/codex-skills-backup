---
name: ai-investment-research
description: Run an AI-native early-stage investment research workflow for startup deals, founder calls, BP decks, notes, company names, candidate evaluation, market sizing, evidence checking, investment memos, diligence questions, deal tracking, meeting consensus, and simulated investor comments. Use when the user asks to review a company or deal, decide whether to invest or follow up, clean founder-call transcripts for investment research, create a one-pager, cross-check claims, attack a startup narrative, draft diligence questions, write an investment memo, estimate market size, audit an AI investment candidate, track deal status, summarize meeting consensus, or predict how Fay might comment on a deal.
---

# AI Investment Research

## Operating Principles

Treat this as an evidence-first investment workflow. Do not invent facts, do not convert founder narrative into verified truth, and do not let a polished story substitute for product traction, retention, distribution, or commercial proof.

Always separate:
- Facts from the provided material.
- Publicly verifiable facts.
- Founder or company claims.
- Analyst inference.
- Missing or unverified information.

When the task requires current company, founder, funding, market, product, or competitor facts, search the web and cite sources. If network access or source access is unavailable, say what could not be verified and mark those claims as unverified.

## Entry Routing

When the user provides deal material or says things like "帮我看看这个项目", "看下这家公司", "这个要不要投", "开始看一个公司", or "项目材料我发你了", run `deal-intake`.

Ask at most two intake questions:
1. Is this the first time looking at the company, or an update to a company already reviewed?
2. If the material type is unclear, is it a founder-call transcript, BP/notes/written material, or only a company name?

After those questions, execute. Do not run a long requirements interview.

Select the pipeline:
- **Mode A - Founder call transcript >= 5000 Chinese characters or equivalent**: run transcript cleaning, one-pager, evidence map, critical attack, diligence questions, investment memo, Fay comments, and full report.
- **Mode B - BP, notes, article, short transcript, or other written material**: run one-pager, question list, Fay comments, and full report. Do not run evidence map, critical attack, or investment memo unless the user asks or the material is rich enough.
- **Mode C - Only company name or almost no material**: collect public information, create one-pager, information gaps, question list, Fay comments if possible, and full report.

If the user provides additional material for an existing company, use incremental review: read prior files if available, create a "本次更新摘要", update conclusions without treating the deal as new.

## Core Workflow

1. Create or identify a local deal folder when working with files. Prefer `deals/{company-name}/` inside the current workspace unless the user has an established location.
2. Preserve raw materials. For transcripts, copy the raw dialogue into the appendix before analysis and keep every sentence.
3. Produce intermediate files only when useful for the task: `intake-card.md`, `one-pager.md`, `evidence-map.md`, `attack.md`, `question-list.md`, `investment-memo.md`, `fay-comment.md`.
4. Produce `full-report.md` as the internal complete record for full deal reviews.
5. If the user has Redoc or another publishing target available, upload only agent-created outputs. Never modify, delete, or move manually added user documents.
6. End full pipeline runs by asking the user to set deal status: Stop, Pending, or Follow. Record the decision when a tracker exists.

## Transcript Rules

For ASR or founder-call transcripts:
- Keep an appendix with the original dialogue, one sentence not deleted.
- Do not start investment analysis until the cleaned transcript and raw appendix are present.
- Clean into at most 10 parent topic trunks using `##` headings, with child trunks using `###` headings.
- Preserve speaker order and time continuity.
- Bold investor-side questions or comments when speaker identity is known.
- Insert calibration notes about every 10 sentences unless the user asks not to.
- After cleaning, verify completeness against the raw transcript and explicitly mention any gaps repaired or unresolved.

## Module References

Read only the relevant reference before executing a module:
- For one-pagers, evidence maps, attacks, questions, memos, candidate audits, market sizing, deal tracking, and meeting consensus, read [modules.md](references/modules.md).
- For Fay comments, use the standalone `fay-investment-comment` skill when available; it owns Fay's preference library and output rules. Keep `fay-comment.md` as this workflow's expected output filename.
- For final document structure and file naming, read [outputs.md](references/outputs.md).

## Decision Quality Checklist

Before finalizing investment analysis, check:
- Are all important numbers sourced or marked as unverified?
- Are founder claims separated from independent evidence?
- Are contradictions and missing evidence explicit?
- Is the strongest bear case included?
- Are next questions designed to validate concrete assumptions rather than sound smart?
- Does the conclusion distinguish Recommend, Pending, Pass, and Insufficient Info?
- Is every deliverable clean enough to send without placeholders?
