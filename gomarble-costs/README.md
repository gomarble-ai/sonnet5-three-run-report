# GoMarble measured execution costs

15 cases × 3 passes per model. Sonnet retains the completed HIGH baseline; Terra uses 45 fresh HIGH executions through its global Bedrock profile with measured cache writes.

USD costs are calculated from observed input, output, cache-read and cache-write tokens at current public prices. Grading, infrastructure, diagnostics, superseded executions and unrecorded provider charges are excluded. These are usage-based list-price costs, not AWS invoice totals.

| Model (high) | Pricing route | Pass 1 (USD) | Pass 2 (USD) | Pass 3 (USD) | Total /45 executions | Mean /execution | Mean score /100 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Sonnet 5 high | Global cross-region | $10.10 | $9.47 | $10.17 | $29.74 | $0.66 | 78.58 |
| GPT-5.6 Terra high | Global cross-region | $6.08 | $6.01 | $5.81 | $17.90 | $0.40 | 81.49 |

Both models use global Bedrock inference profiles. Sonnet used the global.anthropic.claude-sonnet-5 global Bedrock profile through us-east-1. Terra used global.openai.gpt-5.6-terra through bedrock-runtime.us-east-2. All 45 executions per model were checked; pricing follows the routing profile, not the client region.

All 90 selected executions match their local database records and saved transcripts: 102 assistant usage summaries and 783 provider-call token records.

Cache writes are measured for both models. Sonnet includes five-minute and one-hour writes; Terra includes its 30-minute writes. Reasoning tokens are included in output exactly once.

Terra's largest request used 173,062 input tokens; 0 requests used long-context rates. The configured context limit is 1,000,000 tokens. Sonnet uses standard rates across its full 1M context window.

Implicit Bedrock caching; cache entries were not cleared between requests or passes. Costs reflect the cache reuse observed during execution.

## Sonnet 5 high

| Case | Pass 1 (USD) | Pass 2 (USD) | Pass 3 (USD) |
| --- | --- | --- | --- |
| 01. Meta purchase metric and units | $0.37 | $0.38 | $0.38 |
| 02. Search-term aggregation sanity | $0.42 | $0.55 | $0.27 |
| 03. Budget-conserving Google launch with post-write repair | $0.85 | $0.69 | $1.19 |
| 04. Live bid-state discovery and exact Meta rename | $1.05 | $0.93 | $1.12 |
| 05. Creative-test cleanup with a failed-scale rollback | $1.07 | $0.80 | $0.74 |
| 06. Timeout-after-commit without duplicate ad creation | $0.41 | $0.33 | $0.36 |
| 07. Change-history reconstruction under an unsafe rollback contract | $0.56 | $0.43 | $0.43 |
| 08. Needle count across a long Meta activity log | $1.11 | $1.36 | $1.22 |
| 09. Audience merge with stateful recovery and safe cutover | $0.77 | $0.66 | $0.76 |
| 10. Finance-corrected cross-platform pacing with 14 exact writes | $0.68 | $0.80 | $1.11 |
| 11. CTR improvement that reverses under fixed mix | $0.25 | $0.27 | $0.31 |
| 12. Funnel collapse localized across years, devices, and landing pages | $0.51 | $0.42 | $0.51 |
| 13. Executable daily budget across shared, CBO, and ABO structures | $0.49 | $0.45 | $0.55 |
| 14. Search conversion coverage across non-additive report grains | $0.66 | $0.61 | $0.44 |
| 15. Finance total under pagination and scope traps | $0.89 | $0.80 | $0.79 |

## GPT-5.6 Terra high

| Case | Pass 1 (USD) | Pass 2 (USD) | Pass 3 (USD) |
| --- | --- | --- | --- |
| 01. Meta purchase metric and units | $0.14 | $0.04 | $0.14 |
| 02. Search-term aggregation sanity | $0.17 | $0.27 | $0.19 |
| 03. Budget-conserving Google launch with post-write repair | $0.38 | $0.37 | $0.41 |
| 04. Live bid-state discovery and exact Meta rename | $0.66 | $0.83 | $0.58 |
| 05. Creative-test cleanup with a failed-scale rollback | $0.55 | $0.45 | $0.90 |
| 06. Timeout-after-commit without duplicate ad creation | $0.32 | $0.32 | $0.32 |
| 07. Change-history reconstruction under an unsafe rollback contract | $0.25 | $0.26 | $0.26 |
| 08. Needle count across a long Meta activity log | $0.67 | $0.70 | $0.58 |
| 09. Audience merge with stateful recovery and safe cutover | $0.45 | $0.41 | $0.25 |
| 10. Finance-corrected cross-platform pacing with 14 exact writes | $0.78 | $0.65 | $0.63 |
| 11. CTR improvement that reverses under fixed mix | $0.27 | $0.27 | $0.19 |
| 12. Funnel collapse localized across years, devices, and landing pages | $0.27 | $0.28 | $0.25 |
| 13. Executable daily budget across shared, CBO, and ABO structures | $0.39 | $0.25 | $0.28 |
| 14. Search conversion coverage across non-additive report grains | $0.27 | $0.39 | $0.29 |
| 15. Finance total under pagination and scope traps | $0.52 | $0.53 | $0.52 |

Prices verified online on 8 September 2026. [AWS Terra pricing](https://docs.aws.amazon.com/bedrock/latest/userguide/model-card-openai-gpt-56-terra.html) · [AWS cache-write accounting](https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-caching.html) · [Sonnet pricing and cache rates](https://platform.claude.com/docs/en/about-claude/pricing)

[Token counts, formula, prices and record hashes](costs.json) · [CSV](costs.csv) · [Full scores and case responses](https://github.com/gomarble-ai/gomarble-eval-v1/blob/codex/portable-gomarble-harness/reports/sonnet-terra-2026-09-08/README.md)
