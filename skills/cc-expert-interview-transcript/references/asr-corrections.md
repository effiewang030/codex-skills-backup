# ASR Corrections And Hotword Rules

Use this reference before cleaning transcripts that mention AI, VC, founders, products, chips, model names, or company names.

## Hotword Principles

- Prefer the hotword list over personal judgment for spelling, capitalization, hyphens, and spaces.
- Preserve English terms when the speaker used English.
- If the user provides a CSV hotword list, load it before cleaning and match terms against it.
- If a term is uncertain after context review, keep the source phrase and mark `[存疑：可能是 X]` rather than forcing a correction.
- At the end of the transcript, add a short `新增热词/误识别` list for new terms or ASR patterns discovered.

## Common ASR Misrecognitions

| ASR text | Correct term | Context |
|---|---|---|
| 因为拿的卡 | 英伟达的卡 | GPU context |
| 欧派 | OpenAI | AI company |
| 培训 | Pre-Train | model training context |
| 惊超游 | Game Studio | Cantonese/phonetic |
| 地卖 | DeepMind | AI lab |
| 天猫 / 天毛 | TML / Thinking Machine Lab | company name |
| 口袋鼠 | Codex | product name |
| 天文 / 天文三点五 | Claude / Claude 3.5 | model name |
| 泡马特 | 泡泡玛特 | brand |
| 康泰次 / 康泰斯 | Context | AI term |
| a证 / a振 | Agent | AI term |
| brother use | Browser Use | technical term |
| 马斯克（产品名语境） | MasterGo | product name |
| fly马 / 飞马 | Figma | product name |
| 扣定 | Coding | technical term |
| 微韧 | Vision | AI term |
| linear tension | Linear Attention | AI term |
| 三d dance | 3D Dense | AI term |
| cloud code / coser | Claude Code / Claude | product/model context |
| darryl / w | Dario Amodei | person |
| 吴雨欣 | 吴雨昕 | person |
| 龙虾 | OpenClaw | product |
| levote | Lovot | product |
| gbt | GPT | acronym |

## High-Priority Hotword Categories

Prioritize exact spelling for:

- AI companies and models: `OpenAI`, `Anthropic`, `Claude`, `GPT-4`, `GPT-4o`, `Gemini`, `DeepSeek`, `Qwen`, `Llama`, `Mistral`, `xAI`, `Grok`.
- AI techniques: `Attention`, `Transformer`, `RLHF`, `RAG`, `MoE`, `KV Cache`, `Fine-Tuning`, `Post-Train`, `Pre-Train`, `Inference`, `Embedding`, `Benchmark`, `Tokenization`.
- AI products/tools: `Codex`, `Claude Code`, `Cursor`, `Figma`, `Browser Use`, `Perplexity`, `Lovable`, `Manus`.
- VC and investment terms: `ARR`, `MRR`, `GMV`, `DAU`, `MAU`, `CAC`, `LTV`, `NRR`, `Retention`, `SAFE`, `Term Sheet`, `Cap Table`, `Option Pool`, `Pro Rata`, `Moat`, `PMF`.
- Investors/firms: `Sequoia`, `a16z`, `Andreessen Horowitz`, `Benchmark`, `Founders Fund`, `Thrive Capital`, `Lightspeed`, `Khosla Ventures`, `HongShan`, `Qiming`, `ZhenFund`, `Source Code Capital`.
- People: `Sam Altman`, `Dario Amodei`, `Daniela Amodei`, `Jensen Huang`, `Ilya Sutskever`, `Andrej Karpathy`, `Andrew Ng`, `Fei-Fei Li`, `Yann LeCun`, `Yoshua Bengio`, `Liang Wenfeng`.

When the transcript's domain has a specialized vocabulary not covered here, preserve the speaker's likely original term and add it to the final new-hotword list.
