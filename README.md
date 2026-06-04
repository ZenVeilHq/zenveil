<div align="center">

<img src="https://zenveil.dev/logo.png" alt="ZenVeil" width="72" />

# ZenVeil

**Security scanning for AI-generated code — before it ships.**

[![Website](https://img.shields.io/badge/zenveil.dev-live-7C3AED?style=flat-square&logo=vercel&logoColor=white)](https://zenveil.dev)
[![Docs](https://img.shields.io/badge/docs-mintlify-0EA5E9?style=flat-square)](https://zenveil.mintlify.app)
[![Status](https://img.shields.io/badge/status-beta-F59E0B?style=flat-square)]()
[![License](https://img.shields.io/badge/license-proprietary-6B7280?style=flat-square)]()

</div>

---

## What is ZenVeil?

ZenVeil is a developer-first security platform that scans GitHub repositories for secrets, vulnerabilities, dependency risks, and insecure CI/CD pipelines — with AI-powered remediation built in.

Built for the era of AI-generated code, where developers ship faster than security teams can review.

```
$ zenveil scan owner/repo

  Scanning github.com/owner/repo ...

  ● CRITICAL  Hardcoded AWS secret key in src/config.js (line 14)
  ● HIGH      SQL injection risk in routes/users.js (line 87)
  ● HIGH      Dependency lodash@4.17.15 has known CVE-2021-23337
  ● MEDIUM    No branch protection on main
  ● MEDIUM    GITHUB_TOKEN exposed in .github/workflows/deploy.yml
  ● LOW       Missing Content-Security-Policy header

  6 findings  ·  2 critical/high  ·  Scan ID: scn_a3f9b2

  Run `zenveil fix scn_a3f9b2` to get AI-generated patches →
```

---

## Features

| Feature | Free | Pro | Team |
|---|:---:|:---:|:---:|
| Public repo scanning | ✓ | ✓ | ✓ |
| Secret detection | ✓ | ✓ | ✓ |
| Dependency CVE checks | ✓ | ✓ | ✓ |
| AI-powered remediation | — | ✓ | ✓ |
| Private repo scanning | — | ✓ | ✓ |
| CI/CD pipeline analysis | — | ✓ | ✓ |
| GitHub Action integration | — | ✓ | ✓ |
| Team seats + audit logs | — | — | ✓ |

---

## Quick start

**Scan a public repo in 30 seconds — no account needed:**

```
https://zenveil.dev
```

Paste any GitHub URL. Get findings instantly.

**For private repos and CI integration, [create a free account →](https://zenveil.dev/sign-up)**

---

## CI Integration

Add ZenVeil to any GitHub Actions workflow:

```yaml
# .github/workflows/security.yml
name: Security Scan

on: [push, pull_request]

jobs:
  zenveil:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: zenveilhq/action@v1
        with:
          api-key: ${{ secrets.ZENVEIL_API_KEY }}
          fail-on: high
```

> **Note:** The GitHub Action is coming soon. [Join the waitlist →](https://zenveil.dev)

---

## What ZenVeil scans for

**Secrets & credentials**
Hard-coded API keys, tokens, passwords, private keys — caught before they hit your history.

**Dependency vulnerabilities**
CVE matching across npm, PyPI, and Go modules against the latest NVD database.

**Insecure code patterns**
SQL injection, XSS, path traversal, unsafe deserialization — common OWASP Top 10 risks in AI-generated code.

**CI/CD pipeline risks**
Overly permissive tokens, unpinned actions, missing branch protection, exposed secrets in workflow files.

**API surface exposure**
Unauthenticated endpoints, missing rate limits, broken object-level authorization.

---

## Why now?

AI coding assistants (Copilot, Cursor, Claude) write production code at a pace that outstrips manual security review. The patterns they repeat most often — copying from Stack Overflow, regenerating common auth flows, scaffolding CRUD APIs — are also the patterns most likely to contain vulnerabilities.

ZenVeil sits at the merge step: scan before the PR lands, fix before the deploy ships.

---

## Repositories in this org

| Repo | Description | Status |
|---|---|:---:|
| [`zenveilhq/zenveil`](https://github.com/ZenVeilHq/zenveil) | This repo — home, docs, and community | Public |
| [`zenveilhq/ai-security-guardrails`](https://github.com/ZenVeilHq/ai-security-guardrails) | Cursor rules, Claude prompts, OWASP checklists for AI-assisted coding | Public |
| [`zenveilhq/examples`](https://github.com/ZenVeilHq/examples) | Intentionally vulnerable apps and sample scan reports | Public |
| `zenveilhq/action` | Official GitHub Action | Coming soon |
| Core scanner & API | Proprietary | Private |

> The core platform (scanner engine, API, backend) is proprietary and private during beta. Public repos contain community resources, examples, and integrations.

---

## Documentation

Full documentation lives at **[zenveil.mintlify.app](https://zenveil.mintlify.app)**

- [Getting started](https://zenveil.mintlify.app/quickstart)
- [API reference](https://zenveil.mintlify.app/api-reference)
- [CI integration](https://zenveil.mintlify.app/ci-integration)
- [Understanding findings](https://zenveil.mintlify.app/findings)

---

## Security

If you find a security vulnerability in ZenVeil itself, please disclose it responsibly.

**Do not open a public issue.** Email us at **security@zenveil.dev** with:
- A description of the vulnerability
- Steps to reproduce
- Potential impact

We aim to respond within 48 hours and will credit researchers in our changelog.

See [SECURITY.md](./SECURITY.md) for our full disclosure policy.

---

## Community & support

- **Website:** [zenveil.dev](https://zenveil.dev)
- **Docs:** [zenveil.mintlify.app](https://zenveil.mintlify.app)
- **Email:** [hello@zenveil.dev](mailto:hello@zenveil.dev)
- **Issues:** Use GitHub Issues in this repo for docs feedback, examples requests, and community questions. For product bugs, use the in-app feedback button.

---

## License

Community resources in this repository (docs, examples, guardrails) are licensed under [MIT](./LICENSE).

The ZenVeil platform, scanner engine, and API are proprietary software. All rights reserved.

---

<div align="center">

Built for developers who ship fast and sleep well.

**[Start scanning free →](https://zenveil.dev)**

</div>
