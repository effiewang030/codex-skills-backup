---
name: cc-expert-interview-transcript
description: Expert-interview transcript cleaning workflow for VC and diligence calls. Use when the user provides ASR/raw meeting transcript text, Recall/Otter/Feishu exports, expert-call recordings converted to text, founder interviews, diligence calls, informal investment conversations, or asks to turn step1 raw transcript into a faithful step2 Chinese transcript named "cc-专家访谈逐字稿". Produces a high-retention transcript, not a summary, preserving speaker order, data points, questions, judgments, and investment-relevant details.
---

# cc-专家访谈逐字稿

Use this skill to convert ASR raw transcript (`step1`) into a high-quality faithful transcript (`step2`) for expert interviews, founder calls, project diligence, and informal investment conversations.

Core principle: cleaning is not creation. The output should make the reader feel they heard the full conversation. Remove filler words and obvious ASR noise, but do not summarize, rewrite into analysis, reorder by topic, or compress substantive information.

## Workflow

1. Split the full transcript by timestamp into segments of about 10 minutes.
   - Report: `共 N 段，总时长约 XX 分钟`.
   - If timestamps are absent, split by natural conversation blocks and state that the split is approximate.
2. Process one segment at a time.
   - From segment 2 onward, read the previous segment's final 2-3 source sentences and verify the current segment continues directly.
   - Keep all speaker turns and the original order.
   - Clean filler words, repair obvious ASR mistakes, and lightly organize paragraphs.
   - Append each finished segment to the draft before moving on.
   - Report: `第 n 段完成（XX:XX - XX:XX），字数比例 XX%`.
3. Run segment-level retention checks.
   - Calculate source character count and cleaned character count. Chinese characters count as 1, English words count as 1, pure numbers count as 1.
   - `>= 70%`: normal.
   - `< 50%`: stop and restore omitted content before continuing.
4. Finish formatting after all segments are processed.
   - Add the metadata block at the top.
   - Insert `##` topic headings only at natural topic changes. Headings are navigation markers, not permission to reorder content.
   - Identify internal/interviewer speech and mark it blue.
   - Bold only the most important judgment, qualitative conclusion, or prediction sentences.
   - Run the whole-document retention check. Target 75-85%; 65-75% requires omission review; below 65% requires restoration; above 90% means filler cleanup is probably insufficient.

## What To Remove

Remove only non-substantive speech debris:

- Filler sounds and interjections: `嘛`, `呢`, `啊`, `呃`, `嗯`, `哦`, `诶`, `唉`, `哎`, `哇`, `哎呀`, `哎哟`.
- Empty confirmations: `明白`, `懂了`.
- Repeated filler: `对对`, `嗯嗯`, `是是`, `好的好的`, `然后然后`, `就是就是`, `那个那个`, `就就就`, `但但但`.
- Empty transitions: `我想说一下`, `那个什么`.
- Isolated sentence-initial filler such as `那个`, `这个`, `嗯`, `呃`, `诶` when it has no information.
- Pure closing politeness at the very end: `谢谢`, `拜拜`, `感谢`, `再约`.

## What To Preserve

Preserve anything with signal, even if casual or messy:

- Uncertainty and judgment qualifiers: `我觉得`, `可能`, `应该`, `感觉`.
- Natural connectors: `就是说`, `其实`, `反正`.
- Opening confirmations when tied to content: `对，我认为...`.
- Background introductions, context-setting, and informative small talk.
- Every question and follow-up, including seemingly small clarifications.
- Every number, date, product detail, physical description, customer example, competitor comparison, and concrete case.
- Founder or expert claims as spoken; do not convert them into verified facts.
- Investor-side investment logic. Do not drop it as idle chatter.

## Cleaning Rules

- Process sentence by sentence. Do not skip a sentence because it feels repetitive or covered later.
- Keep the original time order. Never move content to another section or group by topic.
- Do not rewrite spoken language into polished written prose. Preserve the speaker's way of saying things.
- Merge consecutive fragments by the same speaker into readable paragraphs.
- Split paragraphs longer than 5-6 sentences at natural semantic breaks.
- Put examples introduced by `比如`, `例如`, or `举个例子` in parentheses when this improves readability.
- Fix obvious ASR homophones based on context. If uncertain, keep the source wording and mark `[存疑：...]`.
- Load `references/asr-corrections.md` when the transcript contains AI, VC, company, product, or founder names, or when ASR terms look suspicious.

## Investment-Interview Rules

- Preserve all data points one by one: financing amount, users, retention, GMV, revenue, cost, margin, usage, supply, demand, conversion, price, and timeline.
- Preserve direct competitor comments in the speaker's original language.
- Mark product-demo moments as `[产品演示]` and keep the key discussion around the demo.
- For meal or informal recordings, mark ordering/service interaction as `[用餐间隙]` and skip it, but preserve substantive discussion among participants.

## Output Format

Use Chinese as the primary language. Preserve English terms when the speaker used English.

Metadata block:

```text
受访者：{姓名}，{公司} {职位/身份}
访谈日期：{YYYY-MM-DD}
访谈者：{访谈方姓名}（{公司}）
录音来源：{链接或文件名}
```

Conversation format:

```markdown
## {自然话题标题}

- <font color="#3357D9">提问方的问题/发言</font>
  - 受访方回答内容第一段。
  - 受访方回答内容第二段。
  - **受访方最核心的判断、定性或预测。**
  - （<font color="#3357D9">针对上一句的具体追问？</font>）受访方对追问的回答直接跟在同一行。
```

Rules:

- Delete timestamps such as `[MM:SS]`.
- Delete raw speaker labels such as `[Speaker 0]`.
- First-level bullets are interviewer questions or new prompts.
- Second-level bullets are interviewee answers. If the same answer naturally breaks into multiple paragraphs, keep multiple second-level bullets.
- Follow-up questions that clarify the current answer stay as second-level parenthetical blue text.
- Internal/interviewer speech is blue: `<font color="#3357D9">...</font>`.
- External interviewee speech remains black.

## Bold Rules

Bold only interviewee sentences that express judgment, qualitative conclusion, comparison, contradiction, or prediction.

Bold when the sentence includes signals such as:

- `根本`, `本质上`, `其实`, `一定`, `最重要的是`.
- `不像...`, `比...更...`, `反而...`.
- `我觉得`, `我判断`, `最终会...`.

Do not bold background narration, names, product terms, isolated numbers, or entire paragraphs. If more than 3 consecutive sentences are bold, reduce to the single highest-signal sentence.

## English And Term Rules

- Preserve English terms the speaker used; do not translate them.
- Capitalize common AI/VC terms and acronyms correctly: `GPU`, `RL`, `API`, `LLM`, `DAU`, `Post-Train`, `Fine-Tuning`, `Inference`, `Embedding`, `Benchmark`.
- Prefer a provided hotword list or `references/asr-corrections.md` over guessing.
- After finishing, list new ASR corrections discovered in this transcript under `新增热词/误识别`.

## Examples

Read `references/examples.md` when the output structure, follow-up formatting, or data-retention standard is unclear.
