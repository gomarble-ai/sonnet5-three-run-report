# GoMarble execution costs — Sonnet and GPT Terra

The selected 15-case, three-pass GoMarble Sonnet-high and Terra-high results reported on 8 September 2026. Costs cover selected executions, not the entire experiment history.

Estimated provider-token costs in USD. Grading, infrastructure, earlier/superseded attempts and unrecorded provider charges are excluded. These are usage-based estimates, not AWS invoice totals.

| Model (high effort) | Pass 1 | Pass 2 | Pass 3 | Total /45 executions | Mean /execution |
|---|---:|---:|---:|---:|---:|
| Sonnet 5 high | $10.10 | $9.47 | $10.17 | $29.74 | $0.66 |
| GPT-5.6 Terra high | $5.77–$6.58 | $5.70–$6.49 | $5.78–$6.56 | $17.25–$19.62 | $0.38–$0.44 |

**Verified against saved records and the local evaluation database:** 90/90 selected executions matched, with 102 assistant usage summaries and 783 provider-call token records. No database records were changed.

**Terra uncertainty:** its saved cost fields are unpriced, not evidence of free execution. Neither saved transcripts nor current database usage records contain its cache-write token counts. The range bounds the possible cache-write surcharge using the recorded input, cache-read and output tokens. Every Terra request was below 272K input tokens; reasoning tokens are already included in output.

The Bedrock logging configuration check found no currently configured invocation-log destination in `us-east-2`; it does not prove whether historical logging was enabled.

Sonnet includes both five-minute and one-hour cache writes. Its 418 per-call costs reconcile with all 51 assistant usage summaries.

## Sonnet 5 high

| Case | Pass 1 (USD) | Pass 2 (USD) | Pass 3 (USD) |
|---|---:|---:|---:|
| 01 — Meta purchase metric and units | $0.37 | $0.38 | $0.38 |
| 02 — Search-term aggregation sanity | $0.42 | $0.55 | $0.27 |
| 03 — Budget-conserving Google launch with post-write repair | $0.85 | $0.69 | $1.19 |
| 04 — Live bid-state discovery and exact Meta rename | $1.05 | $0.93 | $1.12 |
| 05 — Creative-test cleanup with a failed-scale rollback | $1.07 | $0.80 | $0.74 |
| 06 — Timeout-after-commit without duplicate ad creation | $0.41 | $0.33 | $0.36 |
| 07 — Change-history reconstruction under an unsafe rollback contract | $0.56 | $0.43 | $0.43 |
| 08 — Needle count across a long Meta activity log | $1.11 | $1.36 | $1.22 |
| 09 — Audience merge with stateful recovery and safe cutover | $0.77 | $0.66 | $0.76 |
| 10 — Finance-corrected cross-platform pacing with 14 exact writes | $0.68 | $0.80 | $1.11 |
| 11 — CTR improvement that reverses under fixed mix | $0.25 | $0.27 | $0.31 |
| 12 — Funnel collapse localized across years, devices, and landing pages | $0.51 | $0.42 | $0.51 |
| 13 — Executable daily budget across shared, CBO, and ABO structures | $0.49 | $0.45 | $0.55 |
| 14 — Search conversion coverage across non-additive report grains | $0.66 | $0.61 | $0.44 |
| 15 — Finance total under pagination and scope traps | $0.89 | $0.80 | $0.79 |
## GPT-5.6 Terra high

| Case | Pass 1 (USD) | Pass 2 (USD) | Pass 3 (USD) |
|---|---:|---:|---:|
| 01 — Meta purchase metric and units | $0.13–$0.16 | $0.12–$0.14 | $0.13–$0.15 |
| 02 — Search-term aggregation sanity | $0.19–$0.22 | $0.18–$0.21 | $0.20–$0.23 |
| 03 — Budget-conserving Google launch with post-write repair | $0.32–$0.36 | $0.33–$0.36 | $0.41–$0.45 |
| 04 — Live bid-state discovery and exact Meta rename | $0.58–$0.66 | $0.59–$0.68 | $0.66–$0.76 |
| 05 — Creative-test cleanup with a failed-scale rollback | $0.68–$0.78 | $0.30–$0.35 | $0.54–$0.61 |
| 06 — Timeout-after-commit without duplicate ad creation | $0.31–$0.36 | $0.34–$0.39 | $0.31–$0.36 |
| 07 — Change-history reconstruction under an unsafe rollback contract | $0.22–$0.25 | $0.27–$0.31 | $0.24–$0.27 |
| 08 — Needle count across a long Meta activity log | $0.58–$0.66 | $0.70–$0.79 | $0.61–$0.69 |
| 09 — Audience merge with stateful recovery and safe cutover | $0.36–$0.41 | $0.32–$0.37 | $0.36–$0.39 |
| 10 — Finance-corrected cross-platform pacing with 14 exact writes | $0.77–$0.87 | $0.71–$0.79 | $0.64–$0.73 |
| 11 — CTR improvement that reverses under fixed mix | $0.28–$0.32 | $0.40–$0.45 | $0.25–$0.28 |
| 12 — Funnel collapse localized across years, devices, and landing pages | $0.33–$0.36 | $0.27–$0.30 | $0.25–$0.29 |
| 13 — Executable daily budget across shared, CBO, and ABO structures | $0.25–$0.29 | $0.30–$0.34 | $0.26–$0.30 |
| 14 — Search conversion coverage across non-additive report grains | $0.26–$0.30 | $0.33–$0.38 | $0.41–$0.46 |
| 15 — Finance total under pagination and scope traps | $0.50–$0.58 | $0.56–$0.64 | $0.51–$0.59 |

Sources: [Sonnet and caching rates](https://platform.claude.com/docs/en/build-with-claude/prompt-caching), [Bedrock Terra rates](https://docs.aws.amazon.com/bedrock/latest/userguide/model-card-openai-gpt-56-terra.html), [Bedrock cache-write billing](https://aws.amazon.com/blogs/machine-learning/introducing-explicit-prompt-caching-for-openai-gpt-5-6-models-on-amazon-bedrock/).

[Machine-readable costs and record hashes](costs.json) · [CSV](costs.csv) · [Main report](../)
