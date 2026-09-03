<p align="center">
  <img src="logo-transparent.png" alt="ComplyEdge" width="120">
</p>

<h1 align="center">ComplyEdge</h1>

<p align="center">
  <strong>Runtime EU AI Act compliance enforcement. Deterministic. Not probabilistic.</strong>
</p>

<p align="center">
  <a href="https://github.com/ComplyEdge/complyedge/actions/workflows/ci.yaml"><img src="https://github.com/ComplyEdge/complyedge/actions/workflows/ci.yaml/badge.svg" alt="Tests"></a>
  <a href="https://github.com/ComplyEdge/complyedge/actions/workflows/ci.yaml"><img src="https://img.shields.io/badge/Lint-passing-brightgreen" alt="Lint"></a>
  <a href="https://github.com/ComplyEdge/complyedge/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-Apache_2.0-blue.svg" alt="License"></a>
</p>

---

EU AI Act Article 5 and Article 50 runtime deny for AI agents — on every input and output, in production. Classifiers (`eu-ai-act-*`) score the *system*; ComplyEdge denies *this* prompt or output. Article 50 here is unlabeled or deceptive use, not C2PA.

### Quick Start

```bash
pip install complyedge
pip install trustlint
pip install 'complyedge[mcp]'
npx -y @complyedge/mcp
claude mcp add complyedge -- npx -y @complyedge/mcp
pip install 'complyedge[agents]'
```

CI: `uses: complyedge/trustlint-action@v1`

```python
from complyedge import compliance_check

@compliance_check(jurisdiction="EU")
def your_ai_function(text: str) -> str:
    return call_llm(text)  # compliance enforced automatically
```

### Why Deterministic Matters

| Tool | Enforcement | Accuracy | Audit Trail |
|------|-------------|----------|-------------|
| **ComplyEdge** | **Runtime** | **Deterministic (regex + OPA)** | **Article + citation + hash** |
| TraceGov | Runtime | 60–67% | Score only |
| Kosmoy | Gateway | Probabilistic SLM | Confidence score |
| Promptfoo | Pre-deploy | Test-based | No |

### Rule Corpus

64 YAML rules, compiled to 71 OPA/Rego policies (64 leaf policies and 7 package aggregators), of which 51 leaves are the EU AI Act:

- **EU AI Act Article 5** — 9 prohibited practices (social scoring, biometric ID, predictive policing, emotion recognition, ...)
- **EU AI Act Article 50** — 5 transparency obligations (AI disclosure, deepfakes, chatbot identity, watermarking)
- **GPAI Articles 51–55** — 5 obligations (model classification, copyright, documentation, systemic risk, downstream)
- **Other EU AI Act articles** — 11 covering Art 4, 6, 9, 10, 12, 13, 14, 15, 16, 26 and 27
- **GDPR** — 6 (consent, DPIA, erasure, minimisation, breach notification, cross-border transfer)
- **US + global** — 28 across SOX, HIPAA, TCPA, COPPA, PCI DSS, sanctions and prompt security

Every EU AI Act rule is open source, and every blocked request carries a verbatim article citation.

### Repos

| Repo | Description |
|------|-------------|
| [complyedge](https://github.com/ComplyEdge/complyedge) | Open source compliance engine, SDKs, and rules |
| complyedge-platform | Full platform (private, not publicly accessible) |

### Links

- 🌐 [complyedge.io](https://complyedge.io) — Website
- 📖 [Quick Start Guide](https://complyedge.io/docs/quick-start.html)
- 📚 [API Reference](https://complyedge.io/docs/api-reference.html)
- 💰 [Pricing](https://complyedge.io/#enterprise)

---

<p align="center">
  <em>Apache 2.0 · EU AI Act: GPAI obligations carry fines from 2 August 2026</em>
</p>
