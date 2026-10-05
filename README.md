# ⚡ RFC-2602 AI Ingestion Edge Worker (Open Source)

> **Deployable Cloudflare Worker Reference Implementation for RFC-2602 & Context-Ceiling Preservation.**  
> Strips 95% DOM bloat and serves pristine Markdown AST in <15ms to PerplexityBot, SearchBot, and ClaudeBot.

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/quitegoodproject/rfc2602-worker)
[![Specification: RFC-2602](https://img.shields.io/badge/Specification-RFC--2602-09090b.svg)](https://github.com/quitegoodproject/tokenmarkdown/blob/main/docs/spec/RFC-2602.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

---

## 🧭 The Problem This Solves

Frontier AI search engines (Perplexity, ChatGPT Search, Claude Web) enforce a hard **25,000-token retrieval cutoff** (~100 KB). 

Modern web frameworks (React, Next.js, Tailwind CSS) produce 400 KB to 900 KB of raw DOM per page. As a result, **84% of web pages are truncated before their pricing tables, specifications, or FAQs are ingested**.

This open-source Cloudflare Worker intercepts AI crawlers at the edge:
1. **Detects AI Bots:** Identifies `PerplexityBot`, `OAI-SearchBot`, `ClaudeBot`, or `Accept: text/markdown`.
2. **De-bloats HTML:** Strips scripts, styles, SVGs, navbars, and cookie modals.
3. **Serves Semantic Markdown:** Delivers clean GFM Markdown with byte-0 schema tables in `<15ms`.
4. **Fails Open:** Human browser traffic continues to origin servers with zero modification.

---

## 🚀 1-Click Deployment

### Option A: 1-Click Cloudflare Deploy
Click the button below to deploy this worker directly to your Cloudflare account:

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/quitegoodproject/rfc2602-worker)

### Option B: Local CLI Setup

```bash
# Clone the repository
git clone https://github.com/quitegoodproject/rfc2602-worker.git
cd rfc2602-worker

# Install dependencies
npm install

# Test locally
npm run dev

# Deploy to Cloudflare
npm run deploy
```

---

## ⚡ Open-Source vs. Managed Enterprise (AnswerRail)

| Feature | Open-Source Worker (This Repo) | [AnswerRail.com (Managed Rail)](https://answerrail.com) |
| :--- | :---: | :---: |
| **Price** | Free (MIT License) | From $79/mo |
| **Domain Scope** | 1 Domain (Manual Config) | **Multi-Domain Fleet (3 to 100+ Domains)** |
| **AST Parser** | Regex/Heuristic DOM Pruning | **Linkedom Full Virtual DOM Compiler** |
| **Schema Extraction** | Basic JSON-LD regex | **Full Microdata & JSON-LD Byte-0 Synthesis** |
| **Cryptographic Attestation** | ❌ No | **✅ Ed25519 Anti-Slop Signature Headers** |
| **Active Indexing Push** | ❌ Manual | **✅ Instant Bing IndexNow Broadcast (<3s)** |
| **Citation Telemetry** | ❌ Cloudflare Logs only | **✅ Live AI Referral Attribution & Sentinel** |

---

## 📄 Standards & Governance

* **Protocol Specification:** [RFC-2602 Standard Document](https://github.com/quitegoodproject/tokenmarkdown/blob/main/docs/spec/RFC-2602.md)
* **Maintained by:** [The Quite Good Project](https://quitegoodproject.com)
* **License:** MIT © 2026 The Quite Good Project.
