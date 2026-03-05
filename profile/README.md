# Expanso

**Filter data at the source. Keep what matters. Drop what doesn’t.**

Expanso helps teams process, transform, and protect data where it is created — at the edge, in remote sites, or close to systems of record — before shipping it to central platforms.

---

## Public Repositories

### Core Projects

- **[examples.expanso.io](https://github.com/expanso-io/examples.expanso.io)**  
  Practical, production-style pipeline examples for real workloads.

- **[skills.expanso.io](https://github.com/expanso-io/skills.expanso.io)**  
  Official Expanso skills marketplace (OpenClaw, Claude, and MCP-compatible assistants).

- **[mcp.expanso.io](https://github.com/expanso-io/mcp.expanso.io)**  
  MCP server for Expanso documentation with semantic retrieval.

### Supporting Repositories

- **[templates](https://github.com/expanso-io/templates)**  
  Starter templates for getting new Expanso projects running quickly.

---

## Why Expanso

- **Process near the data** to reduce egress, latency, and risk
- **Apply policy early** (PII controls, filtering, enrichment)
- **Keep secrets local** and limit blast radius
- **Compose workflows in YAML** for portable, auditable pipelines

```yaml
pipeline:
  - component: expanso/pii-detect
    inputs:
      data: "{{ .logs }}"

  - component: expanso/pii-redact
    inputs:
      data: "{{ .step1.output }}"
      fields: [email, phone, ssn]

  - component: expanso/s3-upload
    inputs:
      data: "{{ .step2.output }}"
      bucket: my-audit-logs
```

---

## Links

- **Docs:** <https://docs.expanso.io>
- **Website:** <https://expanso.io>
- **Examples:** <https://examples.expanso.io>
- **Community:** <https://discord.gg/expanso>
