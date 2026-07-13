---
name: nic-vc-skills
description: Lightweight router and workflow coordinator for Nic's VC and AI investment research skills. Use when the user asks to use "nic", "nic-vc-skills", "Nic VC workflow", "那套 VC skills", or gives an investment research task that may need routing across deal intake, VC meeting notes, PR filtering, research link reading, hype checking, investor voice mining, high-tech researcher mining, or AI infrastructure analysis.
---

# Nic VC Skills

This is a lightweight entry skill for Nic's VC research stack. Use it to choose the right specialist skill(s), sequence them, and keep the work product coherent.

Do not copy the specialist skills into context unless the task needs them. Route to the smallest useful set.

## Specialist Skills

| Need | Use |
|---|---|
| Turn BP, notes, founder calls, or raw materials into investment work product | `deal-intake` |
| Clean Recall/Otter/Feishu transcript or write IC meeting notes | `vc-meeting-notes` |
| Judge whether media coverage is PR and extract usable facts | `pr-filter` |
| Process research links, reading lists, xlsx trackers, or AI/VC articles into investment analysis | `vc-research-reader` |
| Test whether a hot sector/company is real or hype | `hype-check` |
| Mine a VC/investor's public thinking, quotes, podcasts, blogs, philosophy | `vc-voice-mining` |
| Research a professor, PhD, CTO, technical founder, or deep-tech researcher | `hightech-researcher-mining` |
| Explain AI infra, estimate costs, analyze AI stack/moat, or prep infra/agent researcher meetings | `ai-infra-learner` |

## Routing Rules

### Deal Materials

Use `deal-intake` as the backbone when the user asks for:

- deal intake, one-pager, investment memo, IC material, pre-meeting notes, L1/L2/L3
- "这个项目帮我看看", "收到 BP", "见完创始人", "起个投研稿"
- evidence map, attack, diligence questions, review checklist, decision log

Then add:

- `pr-filter` for media articles or coverage.
- `vc-research-reader` for research links, reading lists, article batches, or xlsx trackers.
- `vc-meeting-notes` for call transcripts or meeting notes.
- `hype-check` when the sector/company story needs reality checking.
- `ai-infra-learner` when the company is AI infra or technical moat is central.
- `hightech-researcher-mining` when founder/researcher quality is central.

### Research Reading

Use `vc-research-reader` when the user provides:

- one or more URLs for VC/AI/tech investment analysis
- an xlsx research tracker or reading list
- "research links", "阅读清单", "批量分析", "网页导读", "投资文章分析"
- requests to save article analyses into folders or update tracker status

Add `pr-filter` first if the main question is source credibility or whether an article is PR.

Add `hype-check` after reading if the user wants a sector/company reality check from the articles.

### Meetings and People

Use `vc-meeting-notes` when the user provides meeting recordings, transcripts, or messy call notes.

Use `vc-voice-mining` for investors and fund partners.

Use `hightech-researcher-mining` for researchers, professors, CTOs, PhDs, technical founders, and experts in robotics, quantum, BCI, AI4S, materials, energy, or other frontier tech.

Use `ai-infra-learner` Mode E for AI infra, RL, agent, GUI agent, model systems, inference, training, or ML systems researchers.

### Market and Company Judgment

Use `hype-check` when the user asks:

- whether a sector is a bubble
- whether demand is real
- whether numbers are sustainable
- whether timing/readiness is right
- whether a hot company is substance or narrative
- whether a scientific/clinical/materials/energy/AI4S direction is investable

Use `pr-filter` before `hype-check` if the key inputs are media articles or press coverage.

### AI Infrastructure

Use `ai-infra-learner` when the user asks about:

- architectures: DeepSeek, MoE, Flash Attention, distributed training, inference serving
- costs: training cost, inference cost, GPU pricing, token pricing
- stack position: app, app infra, inference infra, training infra, hardware
- moat: replacement by OpenAI/Anthropic, open source, cloud providers, NVIDIA
- latest papers or infra researchers

Combine with `hype-check` when the question is "is this investable?"

## Default Workflow

1. Identify the user's actual object: deal, meeting, person, media article, sector, company, or technology.
2. Select the minimal specialist skill(s) from the routing table.
3. If multiple skills apply, state the order in one short sentence.
4. Read each selected specialist skill's `SKILL.md` before doing the task.
5. Keep outputs investment-useful: conclusion first, evidence clearly labeled, uncertainty explicit, next step concrete.

## Evidence Discipline

For investment outputs, preserve the distinction between:

- `事实`: independently verifiable or directly sourced information.
- `BP claim`: founder/company/BP/media claim not yet verified.
- `高概率推论`: reasoned inference with stated basis.
- `观点/建议`: analyst judgment.

If information is missing, say what is missing and name the lowest-cost verification path.

## Output Style

Default language is Chinese unless the user asks otherwise.

Use concise internal-investment style:

- conclusion first
- avoid marketing language
- keep numbers, names, dates, and source labels
- include counterargument or red flag when material
- recommend the next action only when it follows from the analysis

## Avoid

- Do not merge all seven workflows into one giant response unless the user explicitly asks for a full pipeline.
- Do not treat PR, BP, or founder narrative as fact.
- Do not invent data or fill gaps silently.
- Do not run broad web research for every task; search only when current, external, or verifiable facts matter.
