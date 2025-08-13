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
# Product Documentation — Developer Guide
### A Marp-based, version-controlled presentation

22ds3000188@ds.study.iitm.ac.in

---

## Why Marp for Docs?

- **Single source**: Maintain docs as Markdown, build to HTML/PDF/PPTX.
- **Version control**: Review with PRs; diff-friendly.
- **Automation**: CI/CD to publish on release.

---

<!-- Background image slide -->
<!-- _backgroundImage: "https://images.unsplash.com/photo-1526378722484-bd91ca387e72?auto=format&fit=crop&w=1600&q=80" -->
# Architecture at a Glance

- Microservices
- Async messaging
- Observability

---

## Algorithmic Complexity

$$
T(n) = O(n \log n)
$$

$$
T_{\text{batch}}(n) = \sum_{i=1}^{k} c_i(n)
$$

$$
T_{\text{parallel}}(n) \approx \frac{1}{p} \cdot T_{\text{batch}}(n)
$$

---

## Code Example

```ts
import { Client } from "@acme/sdk";

const client = new Client({ apiKey: process.env.ACME_API_KEY });

async function run() {
  const { id, status } = await client.jobs.create({
    input: { documentIds: ["doc_1", "doc_2"] },
    priority: "high",
  });
  console.log({ id, status });
}
run();
