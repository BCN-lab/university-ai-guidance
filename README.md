# Guidelines on Agentic AI use in Research
Agentic AI tools can take actions on your behalf, such as reading files, writing code, running terminal commands, browsing the web, or interacting with software. This makes them powerful, but also risky (see [colloquium slides on agentic AI](https://github.com/Naubody/university-ai-guidance/blob/main/agenticAI_colloquium_MNau.pdf). Before using such tools in university work, please review the following recommendations.

> [!NOTE]
> These guidelines reflect my views based on personal experience and literature research. It does not represent generally agreed-upon conventions or official institutional policy.

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

#### 1.	Inform yourself about AI safety risks before use
Read up on the specific risks of agentic AI systems, especially when they are allowed to use tools, execute code, access files, browse the web, or interact with other software.

*	Read: [Agentic AI Security: Threats, Defenses, Evaluation, and Open Challenges](https://arxiv.org/abs/2510.23883)

*	Read: [Careful adoption of agentic AI services](https://www.cyber.gov.au/business-government/secure-design/artificial-intelligence/careful-adoption-of-agentic-ai-services)

*	Read: [AI Agent Security Cheat Sheet (OWASP)](https://cheatsheetseries.owasp.org/cheatsheets/AI_Agent_Security_Cheat_Sheet.html)

#### 2.	Learn about prompt injection
Prompt injections are attacks that cause an AI system to ignore your instructions, leak information, run unsafe commands, or take harmful actions based on malicious text found in websites, emails, documents, repositories, or other external content. Be especially careful when an agentic AI system reads webpages, emails, PDFs, GitHub repositories, shared documents, or downloaded files. External content may contain hidden or explicit instructions designed to manipulate the model.

*	Read: [LLM Prompt Injection Prevention Cheat Sheet (OWASP)](https://cheatsheetseries.owasp.org/cheatsheets/LLM_Prompt_Injection_Prevention_Cheat_Sheet.html)

#### 3.	Beware of institutional-scale damage
Even without deliberate prompt injection attacks, AI systems have already caused serious damage to institutions when used carelessly or with excessive autonomy. Consider the recent case where an AI system permanently deleted a firm's internal database due to a misunderstood objective. These risks are not hypothetical.

*	Read Guardian article: [Claude AI deletes firm database
](https://www.theguardian.com/technology/2026/apr/29/claude-ai-deletes-firm-database)

#### 4.	Inform your supervisor or project lead
Let your supervisor, PI, manager, or project lead know when you are using agentic AI tools for university-related work. This is especially important for research projects, teaching materials, or administrative work.

#### 5.	Report incidents or near misses 
If you witness that an AI tool accesses something it should not have accessed, that it deleted or changed important files, leaks information, sends unintended messages, or behaves in other ways suspiciously, report it to your supervisor and/or the VU data security services. Report such cases even if the issue was resolved to protocol the event, prevent others from making the same mistakes, and help increase expertise in our department over time. In the event of a (suspected) data breach, please contact the [IT Service Desk](https://vu.nl/en/employee/emergencies/data-leaks-and-other-incidents) immediately on 020-59 80000 or servicedesk.it@vu.nl.

#### 6.	Do not connect agentic AI to institutional systems
Do not connect agentic AI tools to university email, shared drives, student information systems, HR systems, finance systems, research databases, learning management systems, or internal networks. 

#### 7.	Do not give models access to sensitive data
Never provide agentic AI tools with access to confidential, personal, or institutionally sensitive data, including student data and research data. Do not give AI models access to the server or computing cluster.

#### 8.	Do not let an AI analyze your data directly
Do not let an AI analyze raw, sensitive, confidential, personal, institutional, or unpublished research data directly. Instead, use AI tools to help write analysis scripts with dummy or synthetic data, and run those scripts locally yourself.

#### 9.	Never provide credentials or tokens
Never paste passwords, API keys, SSH keys, access tokens, recovery codes, or private certificates into an AI system. Avoid allowing agentic tools to access files or environments where such secrets may be stored.

#### 10. Maintain separation between personal and work accounts
If an agent is operating in a work browser where your personal email or bank account is also logged in, a hallucination or prompt injection could cause the agent to accidentally read, modify, or leak your private personal data (or vice versa). Therefore, keep your personal and professional digital lives separate as much as possible (e.g., different Gmail accounts).

#### 11.	Use sandboxing
Run agentic AI tools only in a restricted environment, such as a sandbox, container, virtual machine, or other isolated workspace. For example, use terminal sandboxing features where available, such as in Antigravity. Dual boot systems with encrypted partitions improve safety as well.

#### 12.	Use a separate device
Ideally, use a separate computer for agentic AI experimentation, especially when testing new or unfamiliar tools. Avoid using your primary work machine, especially if you already foresee risks.

#### 13.	Apply the principle of least privilege
Never give the model full access to your machine, file system, browser, email, cloud storage, institutional accounts, or command line. Grant only the minimum access needed for the specific task at hand.

#### 14.	Enforce boundaries at the system level, not the prompt level
Do not rely on natural language instructions to keep an agent safe (e.g., prompting the model with "Never delete a file"). Natural language boundaries are easily bypassed by the model's own hallucinations or external prompt injections. Instead, enforce boundaries at the infrastructure level. If you don't want the agent to delete files, run it in an environment where it physically lacks write/delete permissions.

#### 15.	Maintain backups and use version control
Always keep backups of your files before using agentic AI tools. This is especially important before allowing a model to edit, move, rename, generate, overwrite, or delete files. For code, documents, data-processing scripts, and configuration files, use version control such as Git. This approach will allow you to recover files that an AI agent changed or deleted outside your control.

#### 16.	Avoid autonomous long-running tasks
Do not let an agent run unattended for extended periods, especially if it has file-system, network, browser, terminal, or account access. Monitor what it is doing and stop it if it behaves unexpectedly.

#### 17.	Review outputs carefully
Do not assume that the model’s output is correct, safe, legal, or ethical. Check code, citations, calculations, summaries, data transformations, and generated text thoroughly before relying on them. Never trust AI-generated content blindly.

#### 18.	Keep the human in control 
Do not allow the model to execute high-impact actions without review. Require confirmation before deleting files, modifying important documents, installing software, sending emails, publishing content, submitting forms, changing permissions, or contacting external services. Reviewing commands requires you to read and understand the respective programming language.

#### 19.	Do not use OpenClaw on university equipment
The use of OpenClaw (or similar aggressively autonomous, unverified open-source agents) is prohibited on university equipment, as it lacks standard safety rails and may execute high-risk terminal commands without user confirmation.

#### 20. Remember that you remain fully responsible and accountable for harm caused by your AI agents

---

## Why not prohibit the use of agentic AI entirely?

A blanket ban on AI agents is unlikely to be effective without the ability to monitor and enforce rules consistently. Paradoxically, a ban may even increase security risks rather than reduce them: students and staff may still use AI agents, but become less likely to ask questions, seek advice, or report mistakes, especially around data protection, security, or unintended access to files and systems. A ban could also raise fairness concerns if similar restrictions do not apply across the wider faculty or university.

We therefore favour an approach based on education, clear expectations, and individual responsibility. AI agents pose real risks, particularly on VU equipment and when sensitive, confidential, institutional, or unpublished research data are involved. These risks are best managed through guidance, transparency, and a culture in which people feel safe to discuss use cases and report concerns early. Our recommendations are intended to set clear boundaries, discourage high-risk use, and promote informed, accountable, and transparent practice, while avoiding the unintended consequences of a total ban.

> [!NOTE]
> This document focuses mainly on security, privacy, and responsible operation of agentic AI systems.
> The use of AI systems may pose other risks as well, including [impaired skill formation and learning](https://arxiv.org/abs/2601.20245), reduced learning, overreliance, bias, hallucinated information, and unclear authorship or attribution.

---

## Further reading (To be extended)

*	[Against the Uncritical Adoption of 'AI' Technologies in Academia](https://zenodo.org/records/17065099)

*	[The uncritical adoption of AI in science is alarming — we urgently need guard rails](https://www.nature.com/articles/d41586-026-01557-x)

*	[I avoid AI tools because thinking is supposed to be hard. It’s what makes us human](https://www.theguardian.com/commentisfree/2026/may/24/ai-tools-thinking-human-hard-coding-writing-technology)

*	[Scientists invented a fake disease. AI told people it was real](https://www.nature.com/articles/d41586-026-01100-y)

*	[AI safety threat arrives ahead of schedule](https://inthewatershed.substack.com/p/the-ai-safety-threat-arrives-ahead)










