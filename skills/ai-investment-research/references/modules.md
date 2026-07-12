# AI Investment Research Modules

Use this reference for detailed module behavior. Keep outputs concise, evidence-backed, and directly useful for investment judgment.

## deal-intake

Purpose: route any deal material into the correct workflow and create an intake card.

Include in `intake-card.md`:
- Company name, material type, first-look vs update, source list, and date.
- Material quality assessment.
- Recommended pipeline mode: A, B, or C.
- Initial stage judgment and biggest unknowns.
- Suggested next modules.

Constraints:
- Ask no more than two intake questions.
- Do not treat updates as new deals.
- For transcripts, require raw appendix preservation before analysis.

## investment-one-pager

Purpose: create a sendable deal overview for an investor.

Use seven sections:
1. One-sentence positioning.
2. Founder/team background: age if available, experience, personality signals, founding history.
3. What the company does: product form, screenshots or product evidence, pain point, user scenario, business model, highlights.
4. Competitor comparison: search around three competitors when possible and compare in a table.
5. Financing: round, valuation, amount, ownership, historical financing table when available.
6. Initial judgment: Recommend, Pending, Pass, or Insufficient Info, based on objective evidence.
7. Next questions, ordered P0 to P5.

Formatting:
- Put an investor comments block at the top: `> ✏ 投资人 Comments：（请在此处补充你的判断和备注）`.
- Insert 1-3 founder quotes when real quotes are available, using block quote plus gray italic HTML.
- Mark every number as one of: 【文档披露】, 【公开报道】, 【创始人口述】, 【我们推测】, 【未核实】.

Constraints:
- Do not treat fundraising ability as PMF.
- Do not treat speaking ability as product ability.
- Do not write future vision as current capability.
- If screenshots or competitors cannot be found, say so clearly.

## evidence-map

Purpose: cross-check claims across user material and public sources.

Build a Claim Registry with 5-15 claims most relevant to investment judgment. For each claim include:
- Claim.
- Source snippets and URLs or document references.
- Source independence: same-source repetition, weak independent, or strong independent.
- Confidence.
- Contradictions.
- Lowest-cost verification path.

Output four evidence layers:
- Facts strongly supported by independent evidence.
- Claims that look multi-sourced but are same-source repetition.
- Key conflicts.
- Important but under-evidenced claims.

Constraints:
- The same party saying the same thing in multiple places is not independent evidence.
- Do not smooth over contradictions.
- If no evidence is found, say "未找到".

## critical-storyline-attack

Purpose: stress-test a startup narrative.

Attack dimensions:
- Product independent existence value.
- Real demand vs demo demand.
- Temporary wrapper around model capability.
- Platform or foundation-model company compression risk.
- Distribution overestimation.
- Retention authenticity.
- Durable workflow value.
- Commercialization beyond theory.
- Founder/team fit.

Output:
- Top three attack points.
- Why each could be fatal.
- Strongest fair rebuttal.
- Evidence that would mitigate the attack.
- Overall anti-fragility judgment.

Constraints:
- Ground attacks in product mechanics, user behavior, market structure, or evidence gaps.
- Include at least one "if I were the opposition, I would argue..." paragraph.

## diligence-question-list

Purpose: generate high-information questions for the next founder/team/customer call.

Read existing context in this priority order when available: `evidence-map.md`, `one-pager.md`, `attack.md`, `intake-card.md`.

Question principles:
- Ask for concrete examples, real data, decision history, abandoned paths, and observed user behavior.
- Avoid generic "what do you think about the future" questions.
- Do not ask questions already answered unless cross-verification is the goal.
- Include both positive thesis validation and adversarial questions.

For each question include:
- Priority: P0, P1, or P2.
- Question.
- Verification target.
- Red flag answer.
- Green signal answer.
- Best person to ask.

## investment-memo

Purpose: create a structured investment judgment memo.

Read existing context in this priority order when available: `evidence-map.md`, `one-pager.md`, `attack.md`, `question-list.md`, `intake-card.md`.

Use 12 sections:
1. Conclusion and recommendation.
2. Core thesis.
3. Supporting evidence.
4. Anti-thesis / bear case.
5. Key assumptions.
6. Biggest risks.
7. TAM and market opportunity.
8. Return Analysis with Base, Mid, Bull scenarios.
9. Deal Structure: valuation, amount, ownership, terms, insider participation, SAFE/CB if relevant.
10. Multi-perspective evaluation: deal team view plus personal judgment and disagreements.
11. Top three verification actions.
12. Final recommendation.

Core questions:
- What real problem is solved?
- What is the wedge?
- Why now?
- What is non-continuous value?
- What is the real moat?
- How does distribution and growth work?
- What is the commercialization path?
- What is the biggest risk?
- What evidence supports and refutes the thesis?
- What must be verified next?

Constraints:
- Do not treat growth as high-quality growth by default.
- Do not treat user love as commercial viability.
- Use "未找到" for missing numbers, quotes, or sources.

## candidate-audit

Purpose: assess candidates for AI-native early-stage investment roles.

Assess:
- Fit with AI-native early-stage investing.
- Evidence of building or using AI workflows in real investment work.
- Founder-facing ability.
- Judgment quality vs ability to speak fluently.
- Integrity, data authenticity, and capability inflation risks.

Output:
- Overall recommendation: strong proceed, proceed, uncertain, or no.
- Strongest evidence.
- Weakest points.
- Red flags.
- Missing information.
- Three to five follow-up questions.

## market-sizing

Purpose: estimate or sanity-check TAM, SAM, SOM, users, revenue, ARPU, retention, penetration, or related market data.

Rules:
- Give ranges before point estimates.
- Define the measurement: users, MAU, DAU, paid users, revenue, ad revenue, total revenue, geography, platform, and time window.
- Use bottom-up and top-down approaches when feasible.
- Mark high-sensitivity assumptions and variables that could change the answer by 10x.
- Explain likely overestimate and underestimate risks.

Output:
- Conclusion range.
- Definition and scope.
- Methods.
- Assumptions.
- Sensitivity analysis.
- Risk of over/under-estimation.

## deal-tracker

Purpose: maintain deal status and next actions.

States:
- Stop: stop tracking.
- Pending: monthly reminder.
- Follow: weekly reminder.
- Portfolio: post-investment outcome review every two months.

Tracker fields:
- Company.
- Status.
- Last update date.
- Available materials.
- Unfinished review checklist items, max three.
- Next action.
- Reminder or automation ID if one exists.

Constraints:
- Do not invent deal status.
- Keep unverified assumptions marked as unverified.
- Do not confuse "currently tracking" with "validated".

## meeting-consensus

Purpose: turn meeting notes, transcripts, or chat logs into consensus, disagreement, and action items.

Output:
- Three to seven core consensus points.
- Open disagreements and unresolved questions, prioritized.
- Good experiences or positive signals.
- Bad experiences or friction.
- Action items with what, why, priority, and risk.

Rules:
- Distinguish fact, opinion, and hypothesis.
- Translate emotion or complaint into an executable issue.
- Do not merely summarize the meeting.

## fay-investment-comment

Purpose: simulate how Fay might comment on a deal, using recorded preferences when available.

Prerequisite:
- At minimum, read `one-pager.md` or equivalent deal context.
- Read [fay-preferences.md](fay-preferences.md) before simulating (judgment dimensions, scoring checklist, historical cases, and verbatim quotes accumulated from Fay's actual feedback). Do not invent private preference records beyond what is recorded there.
- This file is a living knowledge base: every time new Fay feedback, monthly-report quotes, or review cases come in, append them to `fay-preferences.md` rather than replacing existing content. Do not split this into a separate skill.

Evaluate eight dimensions:
- Product sharpness, highest weight.
- Bottom-up vs top-down motion.
- Founder pattern and founder-market fit.
- Strategic disruptiveness.
- Moat authenticity.
- Probability x payoff.
- Competitive landscape.
- Meaningful stake.

Output:
- Eight-dimension prediction table.
- Simulated comments in a direct, concrete, non-academic style.
- Likely decision.
- Historical analogy only if real preference records are available.
- Disclaimer: "模拟预判不代表 Fay 实际判断。"

Constraints:
- Do not fabricate Fay preferences or quotes.
- Do not exceed the evidence in the material.
