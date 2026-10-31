# Awesome-Source-Code-Search-Repository-Browsing

## Top Source Code Search & Repository Browsing Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Code Search Engines, Cross-Repository Browsing & Self-Hosted Indexing Infrastructure*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Source Code Search & Repository Browsing**. These tools enable developers to find, navigate, and understand code across multiple repositories and hosts—searching by literal text, regex, symbol, or path, and jumping to definitions and references across repository boundaries.



**Examples** include FishEye, Sourcegraph, GitHub Code Search, GitLab Code Search, OpenGrok, Black Duck Hub, Zoekt, Hound, Livegrep, and Greptile (the category leaders).



**Open-source emphasis**: Source Code Search is a domain where open-source tooling is **mature at the search engine layer but requires assembly for a complete product**. **Zoekt** is the standout—a trigram-indexed search engine (Apache 2.0) that powers Sourcegraph and GitLab's exact code search, with symbol-aware ranking and JSON/gRPC APIs . **OpenGrok** provides search plus cross-reference browsing (definitions, references, history) for large legacy codebases, particularly C/C++/Java . **Hound** offers a lightweight MIT-licensed regex search server for a few dozen repos . **Sourcebot** positions itself as the open-source Sourcegraph alternative, with multi-repo/branch indexing, regex, boolean logic, code navigation, and an "Ask Sourcebot" AI feature . The critical caveat: **Zoekt is an engine, not a product**—it lacks code navigation and permission sync with git hosts; you need a platform engineer to run it . **FishEye** (Atlassian) is commercial and has been deprioritized, with only infrequent minor releases . **Greptile** is an AI-powered codebase Q&A platform (not traditional search), used by Stripe and Amazon, but it is a SaaS product with no open-source equivalent .



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-products)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[Sourcegraph](https://sourcegraph.com/)**  

  Universal code search and code intelligence platform; searches across any code host, repo, or language with smart filters, hover tooltips, and cross-repository definitions/references. The benchmark for enterprise code search, built on the open-source Zoekt engine .



- **[GitHub Code Search](https://github.com/)**  

  Native code search within GitHub; supports regex, boolean logic, and qualifiers (`repo:`, `org:`, `path:`, `language:`, `symbol:`, `content:`, `is:`) for searching across public and private repositories .



- **[GitLab Code Search](https://about.gitlab.com/)**  

  GitLab's native code search, now powered by **Zoekt** for exact and regex search with filters; Advanced Search remains a fallback for code, comments, commits, merge requests, and wikis .



- **[FishEye (Atlassian)](https://www.atlassian.com/software/fisheye)**  

  Commercial revision-control browser and search engine; provides a read-only window into Subversion, Perforce, CVS, Git, and Mercurial repositories with commit graph and Jira integration. **Deprioritized by Atlassian** with only infrequent minor releases; better for managers reporting on changes than developers searching daily .



- **[Greptile](https://www.greptile.com/)**  

  AI-powered codebase Q&A platform (not traditional search); indexes large codebases so LLMs can answer questions with full context. Used by 250+ companies including Stripe and Amazon for onboarding, debugging, and PR review bots . **SaaS-only**—no open-source equivalent exists.



- **[Black Duck Hub](https://www.blackduck.com/)**  

  Open source security and license compliance platform; while not a code search tool per se, it indexes code to identify open source components and vulnerabilities.



## Open-Source GitHub Projects



### Search Engines (Indexing Layer)



- **[Zoekt](https://github.com/sourcegraph/zoekt)**  

  The most mature open-source **code search engine** available (Apache 2.0); a trigram index that breaks code into overlapping three-character pieces for fast substring and regex queries. Features: **symbol-aware ranking** (improves with Universal ctags), web server, JSON and gRPC APIs. **It is the engine inside Sourcegraph and GitLab's exact code search** . **Critical limitation**: it is an engine with little product around it—**no code navigation and no permission sync with your git host**. With one platform engineer to own it, Zoekt plus a job that pulls your repos covers most of what people used Sourcegraph search for . **The best foundation for building a custom code search platform**.



- **[OpenGrok](https://github.com/oracle/opengrok)**  

  Open-source **search and cross-reference engine** (CDDL 1.0); click a symbol to see where it is defined and used, with history from several version control systems. **Heavier to run than Zoekt** and its UI is dated, but remains a solid choice for a **large C, C++ or Java tree** needing browsable, cross-referenced views of a legacy codebase .



- **[Hound](https://github.com/hound-search/hound)**  

  Small, MIT-licensed **regex search server** with a clean web UI and light memory footprint. Suits a team with **a few dozen repos** that wants "grep, but in a browser, for everyone" . **Limitation**: Hound has made a choice to not bound search response sizes—large queries can produce massive JSON responses that take seconds to render . **Best for small-scale, low-setup deployments**.



### Complete Search Products (Sourcegraph Alternatives)



- **[Sourcebot](https://github.com/sourcebot-dev/sourcebot)**  

  The strongest open-source **Sourcegraph alternative** (self-hosted); indexes repos/branches across multiple code hosts with **regex, boolean logic, repo/language filters**, and trigram indexing for scale . Features: **code navigation** (goto definition, find references) across all repos, built-in file explorer with syntax highlighting, and **"Ask Sourcebot"**—natural language Q&A over your codebase with inline citations . Docker Compose deployment in seconds. **Best for teams wanting a complete, self-hosted code search product** with AI-assisted Q&A—but it requires ongoing infrastructure management and configuration of indexed repos.



### Additional Strong Open-Source Options



- **Livegrep** — Open-source regex search engine for code; noted as performing better than Hound at scale in one practitioner's experience, though eventually replaced by Zoekt . **Verify maintenance status** before adoption.

- **Sourcegraph (self-hosted)** — While Sourcegraph's core is proprietary, it maintains **Zoekt** as open source and offers a free tier for public code. The self-hosted enterprise product is commercial .

- **RepoTrek** — Terminal-first GitHub source browser for exploring repositories without cloning; supports code search, blame, file history, and symbol outlines via a TUI . **Niche**—for developers wanting a terminal-based browsing experience, not a team search platform.



**Frameworks for building custom systems**: For **exact regex search across thousands of repos**, Zoekt is the engine Sourcegraph and GitLab use . For **cross-reference browsing of legacy C/C++/Java**, OpenGrok . For **a few dozen repos with minimal setup**, Hound . For **a complete self-hosted Sourcegraph alternative with AI Q&A**, Sourcebot . No open-source project matches Sourcegraph's **managed code intelligence and integration ecosystem** out of the box—Sourcebot comes closest but requires operational investment.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Code search platforms handling private repository data must comply with organizational access controls and security policies; **self-hosted code search indexes contain your entire codebase** and require proper authentication, encryption, and network isolation.

- **Open-source code search is mature at the engine layer but requires assembly**—Zoekt provides the search engine that powers Sourcegraph and GitLab , and Sourcebot provides a complete self-hosted product . However, **FishEye is deprioritized** by Atlassian , and **Greptile's AI-powered codebase understanding has no open-source equivalent** . Choose based on whether you need raw search (Zoekt), cross-reference browsing (OpenGrok), a complete product (Sourcebot), or AI Q&A (Greptile, commercial only).

- Verify license terms for commercial use; Zoekt uses Apache 2.0 , OpenGrok uses CDDL 1.0 , Hound uses MIT , and Sourcebot is open-source (check repository) .



---



**Made for developers, platform engineers, and organizations building code intelligence infrastructure.**  

Let's make source code search more open, but with clear eyes about the engine-vs-product gap and the AI-powered codebase understanding that remains commercial territory.
