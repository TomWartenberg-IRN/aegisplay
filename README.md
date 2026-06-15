# 🛡️ AegisPlay 

**An explainable SAST playground for code snippets**

🔗 [Try AegisPlay Beta Now](https://aegisplay.net)

*Note: AegisPlay is a closed-source SaaS tool. This repository serves as a public hub for documentation, transparency, bug reports, and collecting feedback from the developer community.*

---

## Why I Built This

As a developer, I frequently found traditional Static Application Security Testing (SAST) tools frustrating. They often throw massive spreadsheets of cryptic alerts at you, cry wolf over standard sandbox policies, or require complex CI/CD pipelines just to scan a 30-line script.

I wanted a simple, low-friction place where I could paste a messy code snippet and instantly get a human-readable explanation of the risks. No noise, no confusing dashboards—just a straightforward breakdown of:

* **What** is wrong?
* **Where** does the issue appear?
* **Why** does it matter?
* **What** would a safer pattern look like?

## What AegisPlay Does

AegisPlay acts as an immediate translation layer for code quality and security. You paste your code, click **Analyze**, and the system triages the snippet. It provides structured, explainable feedback so you understand the exact implications of your architecture and execution paths.

## How It Works (And Why It Isn't Just an LLM Wrapper)

A common pitfall of AI coding tools is blindly sending raw code to a Large Language Model (LLM) and hoping for accurate results, which frequently leads to hallucinations or missed vulnerabilities. 

AegisPlay uses a **hybrid architecture** (similar to optimizing a dual-class build where one handles the raw stats and the other handles the logic):

1.  **Deterministic Engine:** First, a static engine runs pattern matching, telemetry checks, and mode-specific triage. It groups findings by confidence and category, separating actual security risks from sandbox or policy notes (e.g., preventing a bare `import os` from being flagged as a critical exploit).
2.  **AI Engineer Insight:** Only after the deterministic analysis is complete does the AI layer step in. It reads the structured metadata to prioritize the findings and generate a clear, human-readable summary and fix recommendation.

## The Two Modes

To keep feedback relevant, AegisPlay splits analysis into two distinct lenses:

* **Code Audit Mode:** Focuses on maintainability, input validation, overall architecture, duplicate logic, and production-readiness. It helps you clean up messy code.
* **Security Test Mode:** Focuses strictly on exploitability. It hunts for injection paths (SQL, command execution), unsafe deserialization, exposed secrets, and debug configurations.

## Example Workflow

The core UX is designed to minimize cognitive load:
1. Paste your snippet into the editor.
2. Select **Code Audit** or **Security Test**.
3. Click **Analyze**.
4. Read the prioritized *AI Engineer Insight* and explore the distinct finding cards on the right.

## Who It Is For

AegisPlay is built for developers, learners, indie hackers, freelancers, and small teams who want fast, actionable feedback on specific blocks of code without setting up heavy infrastructure. 

## What It Is Not

Let’s set clear expectations:
* **It does not replace an enterprise SAST pipeline.**
* **It does not replace professional human security audits or penetration testing.**
* It is not a guaranteed "100% secure" stamp for your application. It is a playground to assist you in understanding risk.

---

### ⚠️ Privacy and Safety Note

AegisPlay is currently in **public beta**. While the system is designed to be secure, please exercise common sense: **Do not paste production secrets, API keys, credentials, or highly sensitive proprietary code** into the playground. Use it to evaluate patterns, architecture, and sanitized snippets.

---

## Feedback and Bug Reports

Since this is a solo-built beta, I am actively looking for real-world stress testing. If the engine hallucinates, misses a glaring vulnerability, or "cries wolf" over a normal pattern, please let me know. 

You can use the **Issues** tab in this GitHub repository to:
* Report false positives / false negatives
* Request UI/UX improvements
* Suggest new deterministic rules

## Roadmap / Future Ideas
* Refining the deterministic engine to further reduce sandbox noise.
* Expanding robust support for more languages and frameworks.
* Enhancing the "Generate Secure Patch" preview features.

---

**Ready to test your code?** 🔗 [aegisplay.net](https://aegisplay.net)
