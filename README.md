<p align="center">
  <img src="./assets/header.svg" width="100%" alt="Bharath Kumar Rajesh, AI Engineer. Trace view: M.S. CS at Pace, GPA 3.87; production multi-agent platform with 10K+ daily users and 99.5% uptime; upstream open source; agent reliability tooling." />
</p>

<p align="center">
  <a href="https://thebharath.co"><img src="https://img.shields.io/badge/thebharath.co-7C6CF2?style=flat-square&logo=safari&logoColor=white" alt="Portfolio" /></a>
  <a href="https://linkedin.com/in/thebharathkumar"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:bharath.kr702@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email" /></a>
  <a href="https://medium.com/@thebharathkumar"><img src="https://img.shields.io/badge/Medium-000000?style=flat-square&logo=medium&logoColor=white" alt="Medium" /></a>
  <a href="https://twitter.com/passdweed"><img src="https://img.shields.io/badge/X-000000?style=flat-square&logo=x&logoColor=white" alt="X" /></a>
  <a href="https://open.spotify.com/show/4PDEqJu1u06pqcvBFF4BRA"><img src="https://img.shields.io/badge/Podcast-1DB954?style=flat-square&logo=spotify&logoColor=white" alt="Podcast" /></a>
  <a href="https://pypi.org/project/agent-triage/"><img src="https://img.shields.io/pypi/v/agent-triage?style=flat-square&label=agent-triage&color=3FB950&logo=pypi&logoColor=white" alt="agent-triage on PyPI" /></a>
</p>

<h3 align="center">Agents fail quietly. I build the tooling that makes them fail loudly.</h3>

<br/>

## ✅ The receipts

<p align="center">
  <img src="./assets/terminal.svg" width="100%" alt="pytest run: serves 10K daily users, 99.5% uptime, 12 zero-regression releases, 0.92 MRR@5 over 50K docs, caught 4 silent regressions, faramesh PR 33 merged, Springer Nature 2023, AWS SA and Claude on Bedrock certified, no fabricated metrics. 9 passed, 0 fabricated." />
</p>

Every number on this page traces to a production system, a public repo, or a published paper. Where a result is weak, the repo says so.

## 🏗️ In production

**Multi-agent student platform** · Graduate Assistant, Pace University

LangGraph + Claude on Amazon Bedrock. Answers student questions and guides course selection, grounded in each student's own transcripts and university documents, with every student scoped to their own records.

| 10K+ | 99.5% | 12 | 0.92 | 200+ | 4 |
|:---:|:---:|:---:|:---:|:---:|:---:|
| daily users | uptime | zero-regression releases | MRR@5 over 50K+ docs | eval tests per release | silent regressions caught before users |

## 🧭 The reliability stack

Most of what I open-source answers one question: **how do you know an LLM system still works after you change it?** Each tool covers a different stage.

```mermaid
flowchart LR
    subgraph B["① Build"]
        LC["loopcheck<br/>verifier-first agent loop"]
        OD["obindoc<br/>cited, verified RAG"]
    end
    subgraph R["② Route"]
        CF["costfloor<br/>cheapest model, no regression"]
        DG["downgrade<br/>catches router quality loss"]
    end
    subgraph O["③ Observe"]
        AT["agent-triage<br/>ranks failures from OTel traces"]
        SM["super-mcp-eval<br/>evals for MCP servers"]
        MO["mcp-otel-audit<br/>OTel semconv audit"]
    end
    subgraph F["④ Fix"]
        RX["agent-rx<br/>proposes and A/B-tests fixes"]
    end
    B --> R --> O --> F
    F -. lessons .-> B

    classDef build fill:#1e1b4b,stroke:#7C6CF2,color:#e6edf3
    classDef route fill:#1c1917,stroke:#F59E0B,color:#e6edf3
    classDef observe fill:#052e2b,stroke:#10B981,color:#e6edf3
    classDef fix fill:#3b0a24,stroke:#EC4899,color:#e6edf3
    class LC,OD build
    class CF,DG route
    class AT,SM,MO observe
    class RX fix
```

Try one in a few seconds:

```bash
pip install agent-triage
```

## 🚀 Featured work

| Project | What it does | Proof |
|---|---|---|
| [**ForgeSync**](https://github.com/thebharathkumar/ForgeSync) | Financial integration and reconciliation infra. Normalizes invoices across wire formats into one model, scores matches with explainable signals, gates every write-back behind human approval, keeps an immutable audit trail. | TypeScript · 125 unit + 75 integration tests on real Postgres and Redis · scoring runs ~25x faster than ingestion, so the bottleneck is I/O, not the engine |
| [**loopcheck**](https://github.com/thebharathkumar/loopcheck) | Verifier-first agent loop with an HMAC-chained audit log. `loopcheck demo` runs offline in under 2 seconds. | 86 tests · precision 1.00 / recall 0.33 on a 15-file seed set, published with its limitations |
| [**downgrade**](https://github.com/thebharathkumar/downgrade) | Measures silent quality loss when a model router downgrades requests. Six-type regression classifier across Fireworks, OpenRouter, and LiteLLM routing. | OTel GenAI semconv · in active development |
| [**costfloor**](https://github.com/thebharathkumar/costfloor) | Finds the cheapest model per task family with no silent regression against the expensive baseline. Refuses to claim a dollar saving without a real rate card. | 47 tests · CI on Python 3.11 and 3.12 · offline demo in ~0.3s |
| [**agent-triage**](https://github.com/thebharathkumar/agent-triage) | Ranks multi-agent failures by severity, frequency, and recovery from OpenTelemetry or NDJSON traces. CLI, FastAPI dashboard, OTLP receiver. | On PyPI · 220+ tests · 93%+ coverage |
| [**agent-rx**](https://github.com/thebharathkumar/agent-rx) | Closes the loop on agent-triage: diagnoses failures, proposes fixes, A/B-tests them, and learns which fixes are worth making. | Python |
| [**super-mcp-eval**](https://github.com/thebharathkumar/super-mcp-eval) | Eval harness for MCP servers and the agents that use them: schema compliance and tool-selection accuracy. | Wilson 95% CIs · DuckDB · Streamlit |
| [**mcp-otel-audit**](https://github.com/thebharathkumar/mcp-otel-audit) | Public audit of 4 MCP OpenTelemetry instrumentations against OTel semantic conventions v1.40.0. | Fully reproducible · engaged Logfire and MCP Python maintainers |
| [**obindoc**](https://github.com/thebharathkumar/obindoc) | Grounded RAG over a PDF with span-level citations, a verifier loop, and a tamper-evident audit log. | Under 900 lines · 29 tests |

<details>
<summary><b>Applied ML</b></summary>
<br/>

| Project | What it does | Proof |
|---|---|---|
| [**vehicle-damage-detection**](https://github.com/thebharathkumar/vehicle-damage-detection) | YOLO11s-seg fine-tuned on CarDD with imbalance ablation, error analysis, and a robustness suite. Served via FastAPI and Docker. | 0.753 mask mAP50 on held-out data |
| [**streamsense**](https://github.com/thebharathkumar/streamsense) | Multimodal activity recognition on PAMAP2 wearable IMU data with a late-fusion CNN + transformer. | ONNX export · int8 quantization · FastAPI inference |

</details>

## 🔁 Upstream

- [**artie-labs/transfer**](https://github.com/artie-labs/transfer) (Go): 3 PRs covering an Elasticsearch destination, a Kinesis source consumer, and CONTRIBUTING docs
- **faramesh-core**: 9 PRs, including merged #33 (delegation token policy)
- [**Meshery**](https://github.com/meshery/meshery) (Layer5, CNCF): contributions

## 📚 Research

- **A Deep CNN Approach for Identifying Medicinal and Edible Plants in the Western Ghats.** [ICACECS 2023, Atlantis Press (Springer Nature)](https://www.atlantis-press.com/proceedings/icacecs-23/125995742). 89% accuracy. *Corresponding author.*
- **Driver Drowsiness Detection using AI.** [IJARESM, Vol. 11, Nov 2023](https://www.ijaresm.com/sahasransu-mohanty). Dlib eye-aspect-ratio with a Keras CNN, shipped as an Android app.

## 🛠️ Toolbox

<p align="center">
  <img src="https://skillicons.dev/icons?i=py,ts,go,react,nodejs,fastapi,pytorch,postgres,redis,kafka,docker,aws,azure,terraform,linux&perline=15" alt="Stack" />
</p>

**AI / LLM:** Claude, Amazon Bedrock, LangGraph, LangChain, MCP, OpenTelemetry, RAG, LLM evals<br/>
**Backend / Infra:** FastAPI, Fastify, Prisma, Zod, BullMQ, AWS CDK, Terraform, Docker Compose<br/>
**Testing / Data:** pytest, Vitest, Playwright, DuckDB, Streamlit, ONNX

<p align="center">
  <img src="https://img.shields.io/badge/Anthropic-Claude_on_Bedrock-D97757?style=flat-square&logo=anthropic&logoColor=white" alt="Anthropic certification" />
  <img src="https://img.shields.io/badge/AWS-Solutions_Architect_Associate-FF9900?style=flat-square&logo=amazonaws&logoColor=white" alt="AWS SAA" />
  <img src="https://img.shields.io/badge/Red_Hat-RHCSA-EE0000?style=flat-square&logo=redhat&logoColor=white" alt="RHCSA" />
</p>

## 🐍 Shipping log

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/thebharathkumar/thebharathkumar/output/github-snake-dark.svg" />
    <img alt="Contribution graph eaten by a snake" src="https://raw.githubusercontent.com/thebharathkumar/thebharathkumar/output/github-snake.svg" />
  </picture>
</p>

---

<p align="center"><sub>Open to AI Engineer, Applied AI Engineer, and Forward Deployed Engineer roles · NYC, open to relocation · Currently work-authorized on F-1 OPT</sub></p>
