# Expanso

**Edge data processing — filter, transform, and protect data before it leaves the source.**

Expanso Edge runs pipelines where your data lives: on devices, in remote sites, at the network edge. Data is processed locally, so sensitive information never needs to travel to a central server before you've had a chance to act on it.

---

## Open Source Projects

| Repo | Description |
|------|-------------|
| [**examples.expanso.io**](https://github.com/expanso-io/examples.expanso.io) | Production-ready pipeline examples — log processing, PII redaction, schema enforcement, data routing, and more |
| [**expanso-skills**](https://github.com/expanso-io/expanso-skills) | 172+ pre-built skills for OpenClaw, Claude, and MCP-compatible assistants |
| [**mcp.expanso.io**](https://github.com/expanso-io/mcp.expanso.io) | MCP server for Expanso documentation — semantic search for AI assistants |
| [**makoto**](https://github.com/expanso-io/makoto) | Data integrity framework — SLSA-style assurance levels and Data Bills of Materials |

---

## What It Does

- **Process at the edge** — pipelines run on the machine where data is generated
- **Keep credentials local** — API keys and secrets never leave your environment
- **Work with AI assistants** — skills plug directly into Claude, OpenClaw, and any MCP client
- **Compose pipelines** — chain transforms, filters, and outputs in simple YAML

```yaml
# Example: redact PII before sending logs to S3
pipeline:
  - component: expanso/pii-detect
    inputs: { data: '{{ .logs }}' }
  - component: expanso/pii-redact
    inputs: { data: '{{ .step1.output }}', fields: [email, phone, ssn] }
  - component: expanso/s3-upload
    inputs: { data: '{{ .step2.output }}', bucket: my-audit-logs }
```

---

## Get Started

```bash
# Install Expanso Edge
curl -fsSL https://get.expanso.io/edge/install.sh | bash
expanso-edge --version
```

→ [Documentation](https://docs.expanso.io) · [Examples](https://examples.expanso.io) · [Skills Marketplace](https://github.com/expanso-io/expanso-skills)

---

## Community

- 💬 [Discord](https://discord.gg/expanso) — ask questions, share pipelines, get help
- 🌐 [expanso.io](https://expanso.io) — product info and cloud offering
- 📖 [docs.expanso.io](https://docs.expanso.io) — full documentation
