# 🛡️ AegisPlay Security Policy

**Trust, transparency, and data handling guidelines**

> **Note:** This repository does not host the source code for AegisPlay. It serves as a public hub for documentation, feedback, and issue reporting for the hosted SaaS product at [aegisplay.net](https://aegisplay.net).

---

## 1. Security Policy

AegisPlay is built by a developer, for developers.

Trust is the foundation of any security tool, especially one where users may paste code snippets into a web-based playground. This document explains how AegisPlay should be used, what users should avoid submitting, how the analysis flow works at a high level, and how to report security-related concerns.

No exaggerated guarantees. No corporate buzzwords. Just practical guidance.

---

## 2. Responsible Use

AegisPlay is designed as a practical playground to help developers, learners, indie hackers, freelancers, and small teams understand risky code patterns faster.

It provides structured **What / Where / Why / Fix** reports, Code Audit mode, Security Test mode, AI Engineer Insight, and optional Pro workflows such as report export, secure patch generation, and Stealth Mode.

AegisPlay is **not** a replacement for:

* a professional security audit
* a penetration test
* a full enterprise SAST pipeline
* manual review by experienced engineers
* legal or compliance certification

It is a beta tool intended to support understanding, prioritization, and learning.

---

## 3. What Not to Submit

⚠️ **Important: sanitize your code before pasting.**

AegisPlay is a web-based service. You should never paste:

* production secrets
* API keys
* database credentials
* private cryptographic keys
* access tokens
* personally identifiable information
* sensitive customer data
* highly confidential proprietary source code

Use sanitized, isolated snippets or generalized logic whenever possible.

---

## 4. Data Handling Overview

When you click **Analyze**, your code snippet is processed by AegisPlay’s hybrid analysis workflow to generate a report.

At a high level, the workflow combines:

* deterministic checks
* pattern matching
* mode-specific triage
* confidence/category grouping
* sandbox and policy separation
* AI Engineer Insight for explanation and prioritization

Submitted code is used to generate the specific analysis result for that request.

AegisPlay does **not** use submitted code to train underlying AI models.

---

## 5. Standard Mode vs. Stealth Mode

### Standard Mode

When signed in, AegisPlay may retain scan history so users can revisit previous analyses, review findings, and export reports without rerunning the same scan.

### Stealth Mode

Stealth Mode is designed for zero-retention workflows.

When enabled, AegisPlay does not keep scan history for that analysis. This mode is intended for users who want the result without retaining the analyzed snippet in their account history.

Even when using Stealth Mode, users should avoid submitting secrets, credentials, private keys, or highly sensitive production code.

---

## 6. AI Usage Transparency

AegisPlay is not just a thin “send code to an LLM and print the answer” wrapper.

The AI layer is used after structured analysis has already produced categorized findings. Its role is to explain, summarize, and prioritize the results in more human-readable language.

Because an AI model may be involved in explanation or patch suggestions, outputs can occasionally be incomplete, suboptimal, or wrong.

Always review and test AI-generated secure patches before applying them to real code.

---

## 7. Known Limitations

AegisPlay is currently in public beta.

You should expect that the engine may sometimes:

* flag a safe pattern too aggressively
* miss a complex or highly context-dependent issue
* classify something with imperfect severity
* produce an AI-generated explanation that needs human review
* fail to understand application-specific business logic

AegisPlay does not guarantee complete vulnerability coverage.

---

## 8. Reporting Security Issues in AegisPlay Itself

If you discover a security vulnerability in the AegisPlay application or infrastructure itself, such as:

* authentication bypass
* account isolation issue
* billing or subscription bypass
* API abuse path
* private data exposure
* tenant isolation problem

please do **not** open a public GitHub issue with sensitive exploit details.

Instead, report it privately via the contact/support channel listed on [aegisplay.net](https://aegisplay.net), so it can be triaged and patched safely.

---

## 9. Reporting False Positives / False Negatives

If AegisPlay behaves inaccurately on a code snippet, public GitHub Issues are welcome.

Examples:

* a harmless pattern is reported as a critical exploit
* a risky pattern is missed entirely
* Audit Mode and Security Test Mode prioritize something incorrectly
* a finding is technically correct but poorly explained
* the suggested fix is incomplete or misleading

Please provide a **minimal sanitized snippet** and explain what the engine got wrong.

Do not include production secrets or sensitive proprietary code.

---

## 10. Contact / GitHub Issues Guidance

Use GitHub Issues for:

* false positives
* false negatives
* UI bugs
* confusing output
* feature requests
* documentation improvements

Use private contact via the website for:

* vulnerabilities in AegisPlay itself
* account or billing issues
* sensitive security reports
* anything involving private data or exploit details

Main website: https://aegisplay.net
