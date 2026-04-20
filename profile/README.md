<p align="center">
  <img src="https://raw.githubusercontent.com/ComplyEdge/complyedge/main/logo-transparent.png" alt="ComplyEdge" width="120">
</p>

<h1 align="center">ComplyEdge</h1>

<p align="center">
  <strong>Runtime EU AI Act compliance enforcement. Deterministic. Not probabilistic.</strong>
</p>

<p align="center">
  <a href="https://github.com/ComplyEdge/complyedge-platform/actions/workflows/test.yml"><img src="https://github.com/ComplyEdge/complyedge-platform/actions/workflows/test.yml/badge.svg" alt="Tests"></a>
  <a href="https://github.com/ComplyEdge/complyedge-platform/actions/workflows/lint.yml"><img src="https://github.com/ComplyEdge/complyedge-platform/actions/workflows/lint.yml/badge.svg" alt="Lint"></a>
  <a href="https://github.com/ComplyEdge/complyedge-platform/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-Apache_2.0-blue.svg" alt="License"></a>
</p>

---

ComplyEdge enforces EU AI Act Articles 5, 50, and GPAI obligations (51–55) at runtime — on every AI input and output, in production, under 70ms.

### Quick Start

```bash
pip install complyedge
```

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

25 YAML rules across 3 regulation groups:

- **EU AI Act Article 5** — 7 prohibited practices (social scoring, biometric ID, predictive policing, emotion recognition, ...)
- **EU AI Act Article 50** — 4 transparency obligations (AI disclosure, deepfakes, chatbot identity, watermarking)
- **GPAI Articles 51–55** — 5 obligations (model classification, copyright, documentation, systemic risk, downstream)
- **GDPR, SOX, HIPAA, TCPA, COPPA, PCI DSS** — US + Global regulations

### Repos

| Repo | Description |
|------|-------------|
| [complyedge](https://github.com/ComplyEdge/complyedge) | Open source compliance engine, SDKs, and rules |
| [complyedge-platform](https://github.com/ComplyEdge/complyedge-platform) | Full platform (private) |

### Links

- 🌐 [complyedge.io](https://complyedge.io) — Website
- 📖 [Quick Start Guide](https://complyedge.io/docs/quick-start.html)
- 📚 [API Reference](https://complyedge.io/docs/api-reference.html)
- 💰 [Pricing](https://complyedge.io/pricing.html)

---

<p align="center">
  <em>Apache 2.0 · EU AI Act enforcement starts August 2, 2026</em>
</p>
