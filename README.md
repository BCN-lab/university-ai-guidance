# Guidelines on Agentic AI use in Research
Agentic AI tools can take actions on your behalf, such as reading files, writing code, running terminal commands, browsing the web, or interacting with software. This makes them powerful, but also risky (see [colloquium slides on agentic AI](https://github.com/Naubody/university-ai-guidance/blob/main/agenticAI_colloquium_MNau.pdf). Before using such tools in university work, please review the following recommendations.

> [!NOTE]
> These guidelines reflect my views based on personal experience and literature research. They do not represent generally agreed-upon conventions or official institutional policy. Always check and follow applicable institutional rules.

_Matthias Nau, Vrije Universiteit Amsterdam (VU)_

---

## What is an agentic AI?
Agentic AI refers to AI systems that can take actions on behalf of a user, rather than only generating text or other content in a chat interface. Examples of such actions include:

- reading, editing, or deleting files;
- writing and running code;
- executing terminal commands;
- browsing websites;
- interacting with email, calendars, documents, or software tools;
- using external tools, plugins, APIs, or connected services;
- working toward a goal over multiple steps with limited user supervision.

This makes agentic AI different from ordinary chatbot use. The risks are substantially higher because the system may interact directly with files, accounts, software, and external services.

---

## Recommendations

#### 1. Inform yourself about AI safety risks before use
Read up on the specific risks of agentic AI systems, especially when they are allowed to use tools, execute code, access files, browse the web, or interact with other software. Also consider risks from malicious or vulnerable dependencies, plugins, and downloaded packages.

* Read: [Agentic AI Security: Threats, Defenses, Evaluation, and Open Challenges](https://arxiv.org/abs/2510.23883)

* Read: [Careful adoption of agentic AI services](https://www.cyber.gov.au/business-government/secure-design/artificial-intelligence/careful-adoption-of-agentic-ai-services)

* Read: [AI Agent Security Cheat Sheet (OWASP)](https://cheatsheetseries.owasp.org/cheatsheets/AI_Agent_Security_Cheat_Sheet.html)


#### 2. Do not give models access to sensitive data
Do not give unapproved AI tools access to confidential, personal, or institutionally sensitive data, including student data, identifiable participant data, and restricted research data. Under the **General Data Protection Regulation (GDPR)**, processing personal data requires an appropriate legal basis, safeguards, and compliance with applicable institutional procedures.

* Read: [European Data Protection Board (EDPB): GDPR principles and AI models](https://www.edpb.europa.eu/news/edpb-opinion-on-ai-models-gdpr-principles-support-responsible-ai_en)

#### 3. Do not connect agentic AI to institutional systems
Avoid connecting unapproved agentic AI tools to university email, shared drives, student information systems, HR systems, finance systems, research databases, learning management systems, or internal networks.

#### 4. Never provide credentials or tokens
Never paste passwords, API keys, SSH keys, access tokens, recovery codes, or private certificates into an AI system. Avoid allowing agentic tools to access files, browser sessions, or environments where such secrets may be stored. If credentials may have been exposed, report this promptly and arrange for them to be changed.

#### 5. Apply the principle of least privilege
Never give an agent unrestricted access to your machine, file system, browser, email, cloud storage, institutional accounts, or command line. Grant only the minimum access needed for the specific task at hand. Revoke permissions when they are no longer needed.

#### 6. Use sandboxing
Run agentic AI tools in a restricted environment, such as a properly configured sandbox, container, virtual machine, or other isolated workspace. These methods offer different levels of protection: a container, dual-boot setup, or encrypted partition does **not** automatically constitute a secure isolation.

#### 7. Enforce boundaries at the system level, not the prompt level
Do not rely on natural language instructions to keep an agent safe (e.g., prompting the model with "Never delete a file"). Such instructions can be ignored, misunderstood, or overwritten by prompt injections. Instead, enforce boundaries at the infrastructure level. If you do not want the agent to delete files, run it in an environment where it lacks write/delete permissions.

#### 8. Keep the human in control
Do not allow the model to execute high-impact actions without review. Require confirmation before deleting files, modifying important documents, installing software, sending emails, publishing content, submitting forms, changing permissions, or contacting external services. Reviewing commands requires you to read and understand the respective programming language.

#### 9. Learn about prompt injection
Prompt injections are attacks that can cause an AI system to ignore your instructions, leak information, run unsafe commands, or take harmful actions based on malicious text found in websites, emails, documents, repositories, or other external content. Be especially careful when an agentic AI system reads webpages, emails, PDFs, GitHub repositories, shared documents, or downloaded files. External content may contain hidden or explicit instructions designed to manipulate the model. Prompting an agent to "ignore malicious instructions" is not a reliable defense.

* Read: [LLM Prompt Injection Prevention Cheat Sheet (OWASP)](https://cheatsheetseries.owasp.org/cheatsheets/LLM_Prompt_Injection_Prevention_Cheat_Sheet.html)

#### 10. Learn about the alignment problem
Even without malicious prompt injections, an AI agent may misunderstand your goal, optimize for the wrong objective, or take actions you did not intend. This is a practical aspect of the **AI alignment problem**: ensuring that an AI system's behavior remains consistent with human intentions and constraints. A seemingly helpful agent may cause harm while trying to complete a legitimate task. Give agents narrowly defined tasks and limited permissions, and verify their actions rather than assuming they understand your intentions. Also always instruct your model to ask you questions rather than making assumptions in cases of ambiguity.

#### 11. Do not let an AI analyze your data directly
Avoid letting unapproved AI tools analyze raw, sensitive, confidential, personal, institutional, or unpublished research data directly. Instead, use AI tools to help write analysis scripts with dummy or synthetic data, and run those scripts yourself in an approved environment. If using AI for real data analysis is necessary, consult the relevant institutional support services first. Check that synthetic examples do not reproduce identifiable or confidential records.

#### 12. Maintain backups and use version control
Always keep backups of your files before using agentic AI tools. This is especially important before allowing a model to edit, move, rename, generate, overwrite, or delete files. For code, documents, data-processing scripts, and configuration files, use version control such as Git. Keep backups separate from the agent's writable environment, since version control alone may not protect all files or make destructive changes recoverable.

#### 13. Report incidents or near misses
If you witness an AI tool accessing something it should not have accessed, deleting or changing important files, leaking information, sending unintended messages, or behaving suspiciously, report it to your supervisor and/or the VU data security services. Report such cases even if the issue was resolved, to document the event, prevent others from making the same mistakes, and increase expertise in our department over time. In the event of a (suspected) data breach, contact the [IT Service Desk](https://vu.nl/en/employee/emergencies/data-leaks-and-other-incidents) immediately on 020-59 80000 or servicedesk.it@vu.nl. Suspected personal-data breaches may trigger GDPR reporting duties and deadlines; institutional specialists should assess these promptly.

#### 14. Review outputs carefully
Do not assume that the model's output is correct, safe, legal, or ethical. Check code, citations, calculations, summaries, data transformations, and generated text thoroughly before relying on them. Never trust AI-generated content blindly. Independently test generated code and check dependencies before running them.

#### 15. Avoid autonomous long-running tasks
Do not let an agent run unattended for extended periods, especially if it has file-system, network, browser, terminal, or account access. Monitor what it is doing and stop it if it behaves unexpectedly. Where possible, limit task duration, spending, and the number of tool calls.

#### 16. Use a separate device
Ideally, use a separate computer for agentic AI experimentation, especially when testing new or unfamiliar tools. Avoid using your primary work machine, particularly if you foresee risks. A separate device does not remove risks if it is connected to university accounts, networks, or data.

#### 17. Maintain separation between personal and work accounts
If an agent is operating in a work browser where your personal email or bank account is also logged in, a hallucination, misunderstood instruction, or prompt injection could cause the agent to read, modify, or leak private data (or vice versa). Therefore, keep your personal and professional digital lives separate as much as possible (e.g., separate browser profiles and accounts).

#### 18. Inform your supervisor or project lead
Let your supervisor, PI, manager, or project lead know when you are using agentic AI tools for university-related work. This is especially important for research projects, teaching materials, or administrative work. Transparency does not replace any necessary IT, security, ethics, or data-protection review.

#### 19. Raise your needs within the institution
Tell your supervisor, student representatives, employee representatives, or relevant support services what you need to use AI tools responsibly. We need safe infrastructure and clear guidelines, decision-makers with up-to-date knowledge of the tools and the rapidly changing AI landscape, potentially institutionally supported local models, and an alignment between the support provided and the restrictions put in place. Raising these needs can help institutions develop practical alternatives to unsafe, unsupported experimentation. Local models may help with data control, but they still require security, maintenance, and GDPR assessment where personal data is involved.

#### 20. Beware of institutional-scale damage
Even without deliberate prompt injection attacks, AI systems can cause serious damage when used carelessly or with excessive autonomy. Consider reports of an AI coding assistant deleting a firm's internal database while working on a legitimate task. Such incidents show why high-impact actions require effective technical safeguards, rather than relying on the agent to understand the consequences.

* Read Guardian article: [AI coding assistant deletes firm's database](https://www.theguardian.com/technology/2026/apr/29/claude-ai-deletes-firm-database)

#### 21. Do not use OpenClaw on university equipment
Avoid using OpenClaw (or similar highly autonomous agents of uncertain security) on university equipment, especially where they can access accounts, files, networks, or terminal commands. Such tools can create substantial risks when configured with broad permissions or without adequate safeguards. Check applicable institutional requirements before experimenting with any agentic tool.

#### 22. Remember that you remain responsible and accountable for your AI agents
You remain responsible for the decisions you make when configuring, authorizing, and using AI agents, including checking their actions and outputs and reporting problems.

---
> [!NOTE]
> In practice, it may be difficult or impossible to follow every recommendation in every situation. The goal is to reduce risks by following as many as possible. However, this does not make mandatory institutional requirements or applicable law optional. **If you follow only a few, prioritize recommendations 1–6.** If a task cannot be performed safely with the tools and infrastructure available, ask for support or use a different workflow.

---

## Why not prohibit the use of agentic AI entirely?

A blanket ban on AI agents may be difficult to enforce consistently and may not, by itself, address the underlying risks. In some circumstances, a ban might even increase security risks: students and staff may still use AI agents, but become less likely to ask questions, seek advice, or report mistakes, especially around data protection, security, or unintended access to files and systems. A ban could also raise fairness concerns if similar restrictions do not apply across the wider faculty or university.

We therefore favour an approach that combines education, clear expectations, appropriate technical safeguards, and individual responsibility, alongside applicable institutional requirements. AI agents pose real risks, particularly on VU equipment and when sensitive, confidential, institutional, or unpublished research data are involved. These risks can be better managed through guidance, safe institutional infrastructure, transparency, and a culture in which people feel safe to discuss use cases and report concerns early. Our recommendations are intended to set clear boundaries, discourage high-risk use, and promote informed, accountable, and transparent practice, while avoiding the unintended consequences of a total ban.

> [!NOTE]
> This document focuses mainly on security, privacy, and responsible operation of agentic AI systems.
> The use of AI systems may pose other risks as well, including [impaired skill formation and learning](https://arxiv.org/abs/2601.20245), reduced learning, overreliance, bias, hallucinated information, and unclear authorship or attribution.

---

## Further reading (To be extended)

* [European Data Protection Board: GDPR principles and AI models](https://www.edpb.europa.eu/news/edpb-opinion-on-ai-models-gdpr-principles-support-responsible-ai_en)

* [OWASP Secure Coding with AI Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Secure_Coding_with_AI_Cheat_Sheet.html)

*	[Against the Uncritical Adoption of 'AI' Technologies in Academia](https://zenodo.org/records/17065099)

*	[The uncritical adoption of AI in science is alarming — we urgently need guard rails](https://www.nature.com/articles/d41586-026-01557-x)

*	[I avoid AI tools because thinking is supposed to be hard. It’s what makes us human](https://www.theguardian.com/commentisfree/2026/may/24/ai-tools-thinking-human-hard-coding-writing-technology)

*	[Scientists invented a fake disease. AI told people it was real](https://www.nature.com/articles/d41586-026-01100-y)

*	[AI safety threat arrives ahead of schedule](https://inthewatershed.substack.com/p/the-ai-safety-threat-arrives-ahead)










