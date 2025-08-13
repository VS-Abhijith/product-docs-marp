---
marp: true
theme: product-docs
math: katex
paginate: true
size: 16:9
title: "Product Docs: Developer Guide"
description: "Marp-driven documentation deck"
author: "Abhijith VS"
---

<!-- _class: lead -->
# Product Documentation<br/>— Developer Guide
### A Marp-based, version-controlled presentation

📧 **Contact:** 22ds3000188@ds.study.iitm.ac.in

<!-- presenter: Open with the motivation for keeping product docs in version control and the benefits of Marp (single source → HTML/PDF/PPTX). -->

---

<!-- _class: compact -->
## Why Marp for Docs?

- **Single source**: Maintain docs as Markdown, build to HTML/PDF/PPTX.
- **Version control**: Review with PRs; diff-friendly.
- **Automation**: CI/CD to publish on release.

**Directives in use:** `theme: product-docs`, `math: katex`, `paginate: true`, `_class` for layout.

<!-- presenter: Reinforce that engineering teams already review Markdown and code; this fits naturally into their workflow. -->

---

<!-- Background image slide -->
<!-- _backgroundImage: "https://images.unsplash.com/photo-1526378722484-bd91ca387e72?auto=format&fit=crop&w=1600&q=80" -->
<!-- _color: #ffffff -->
<!-- _class: lead inverse overlay -->
# Architecture at a Glance

- Microservices
- Async messaging
- Observability (traces, logs, metrics)

<!-- presenter: Call out the image is illustrative; actual architecture diagrams should be embedded as images generated from source (e.g., PlantUML, Mermaid exports). -->

---

## Algorithmic Complexity (Math)

We often summarize performance with **Big-O**:

$$
T(n) = O(n \log n)
$$

For a batched pipeline with \(k\) stages and per-stage cost \(c_i(n)\):

$$
T_{\text{batch}}(n) = \sum_{i=1}^{k} c_i(n)
$$

If parallelized across \(p\) workers (ideal):

$$
T_{\text{parallel}}(n) \approx \frac{1}{p} \cdot T_{\text{batch}}(n)
$$

<!-- presenter: Give a concrete example from your product—e.g., indexing documents and sharding across workers. -->

---

## Code Example (API client)

```ts
// TypeScript SDK: minimal example
import { Client } from "@acme/sdk";

const client = new Client({ apiKey: process.env.ACME_API_KEY });

async function run() {
  const { id, status } = await client.jobs.create({
    input: { documentIds: ["doc_1", "doc_2"] },
    priority: "high",
  });
  console.log({ id, status });

  // Exponential backoff (O(log n) retries)
  let attempt = 0;
  while (attempt < 5) {
    const job = await client.jobs.get(id);
    if (job.status === "done") return job.result;
    await new Promise(r => setTimeout(r, 2 ** attempt * 250));
    attempt++;
  }
}
run().catch(console.error);
