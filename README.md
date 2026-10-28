# GH-300 study guide and practice questions

GH-300 is the exam for the GitHub Copilot certification, delivered through Microsoft Learn and Pearson VUE. It is for developers, DevOps engineers, and the people who roll Copilot out to a team, and it tests responsible use, Copilot features in the IDE, CLI, and on GitHub, how Copilot handles data, prompt crafting, and the policies and content exclusions admins configure. This repository holds a study guide mapped to the current skills outline, a study plan for four weeks, a cheat sheet of plans, policies, and file locations, and 15 original practice questions with explanations.

> Unofficial study notes by [Examice](https://examice.com/exams/microsoft/gh-300?utm_source=github&utm_medium=social&utm_campaign=gh-300-study-guide-and-practice-questions&utm_content=link_1). Not affiliated with or endorsed by GitHub or Microsoft. The practice questions are original and are not taken from the exam.

## Contents

- [Exam at a glance](#exam-at-a-glance)
- [What the exam covers](#what-the-exam-covers)
- [Study plan](#study-plan)
- [Cheat sheet](#cheat-sheet)
- [Free official resources](#free-official-resources)
- [Practice questions](#practice-questions)
- [Exam day tips](#exam-day-tips)
- [FAQ](#faq)
- [Contributing](#contributing)
- [License](#license)

## Exam at a glance

| Item | Official detail |
| --- | --- |
| Certification | GitHub Copilot |
| Exam | GH-300: GitHub Copilot |
| Level | Intermediate |
| Exam time | 100 minutes |
| Questions | 60 scored multiple choice questions plus about 10–15 unscored pretest items, varying by exam |
| Passing score | 700 or greater, on a scaled range of 1–1,000 |
| Price | $99 USD in the United States; regional pricing may apply |
| Delivery | Proctored by Pearson VUE, at a test center or online |
| Open book | No. Microsoft Learn is not available during GitHub exams. |
| Languages | English, Spanish, Portuguese (Brazil), Korean, and Japanese |
| Skills outline | Current as of August 7, 2026 |
| Validity | 2 years. GitHub is moving to Microsoft's recertification process; certifications that expire before it is ready are extended by 6 months. |
| Retakes | 24 hours after a first failed attempt, then 14 days before each later attempt, with at most 5 attempts a year |

Source: [Microsoft Learn certification page](https://learn.microsoft.com/en-us/credentials/certifications/github-copilot/), [GH-300 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/gh-300), [GitHub Learn credentials and FAQ](https://learn.github.com/credentials), [exam duration and experience](https://learn.microsoft.com/en-us/credentials/support/exam-duration-exam-experience), [exam scoring](https://learn.microsoft.com/en-us/credentials/certifications/exam-scoring-reports), and [retake policy](https://learn.microsoft.com/en-us/credentials/support/retake-policy), checked October 28, 2026.

## What the exam covers

| Domain | Weight |
| --- | --- |
| Use GitHub Copilot responsibly | 15–20% |
| Use GitHub Copilot features | 25–30% |
| Understand GitHub Copilot data and architecture | 10–15% |
| Apply prompt engineering and context crafting | 10–15% |
| Improve developer productivity with GitHub Copilot | 10–15% |
| Configure privacy, content exclusions, and safeguards | 10–15% |

Source: [GH-300 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/gh-300), skills measured as of August 7, 2026, checked October 28, 2026. The study guide's summary list also shows a seventh entry, "GitHub Copilot features (25–30%)", with no skills under it, and the certification page repeats it. This guide treats it as a duplicate of "Use GitHub Copilot features". The guide also notes that most questions cover generally available features, with commonly used preview features possible.

Copilot changes fast. This guide uses the names in the GitHub docs on the check date: **Copilot cloud agent** is the agent that works on GitHub in its own environment and opens pull requests (the REST API section is still titled coding agent management), and usage is billed in **GitHub AI Credits**. If your course material uses older names, map them with the docs.

The skills below are a summary in our own words. Read the official study guide for the full list.

### Use GitHub Copilot responsibly

- **Risks and limits of generative AI.** Copilot can produce code that looks right but is wrong, insecure, biased toward common languages and styles, or close to public code. Know the harms, who they affect, and how to reduce them. Docs: [Responsible AI with GitHub Copilot module](https://learn.microsoft.com/en-us/training/modules/responsible-ai-with-github-copilot/), [application card for inline suggestions](https://docs.github.com/en/copilot/responsible-use/inline-suggestions), [Copilot Chat](https://docs.github.com/en/copilot/responsible-use/chat), [agents](https://docs.github.com/en/copilot/responsible-use/agents).
- **Validating output.** Review, test, and scan everything Copilot writes before you rely on it, and keep a human in the loop for agent work. Docs: [risks and mitigations for Copilot cloud agent](https://docs.github.com/en/copilot/concepts/security-governance-and-network-settings/risks-and-mitigations).

### Use GitHub Copilot features

- **Copilot in the IDE.** Turn Copilot on, then use inline suggestions, next edit suggestions, chat, inline chat, and agent mode. Know that content exclusion applies differently by IDE and mode. Docs: [Copilot in IDEs](https://docs.github.com/en/copilot/concepts/copilot-surfaces/copilot-in-ides), [feature matrix](https://docs.github.com/en/copilot/reference/copilot-feature-matrix), [agent mode](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/use-copilot-agents/use-agent-mode).
- **Copilot CLI.** Know what the CLI is for, how to install and sign in, the interactive and programmatic modes, plan mode, sessions, tool approval, and using it to write scripts and manage files. Docs: [about Copilot CLI](https://docs.github.com/en/copilot/concepts/copilot-surfaces/copilot-cli), [install](https://docs.github.com/en/copilot/how-tos/copilot-cli/set-up-copilot-cli/install-copilot-cli), [command reference](https://docs.github.com/en/copilot/reference/copilot-cli-reference/cli-command-reference).
- **Agents, review, and context features.** Use agent mode, edit mode, and MCP servers; manage agent sessions and hand work to other agents; request Copilot code review; use Copilot Spaces, GitHub Spark, pull request summaries, custom instructions, and prompt files; know Copilot Chat's commands, limits, and feedback options. Docs: [about Copilot agents](https://docs.github.com/en/copilot/concepts/agent-capabilities/about-agents/about-github-copilot-agents), [MCP](https://docs.github.com/en/copilot/concepts/customizations/mcp), [code review](https://docs.github.com/en/copilot/concepts/agent-capabilities/agent-powered-workflows-and-operations/code-review), [Spaces](https://docs.github.com/en/copilot/concepts/prompting-and-context/spaces), [custom instructions](https://docs.github.com/en/copilot/concepts/prompting-and-context/custom-instructions), [prompt files](https://docs.github.com/en/copilot/concepts/prompting-and-context/prompt-files), [Chat cheat sheet](https://docs.github.com/en/copilot/reference/chat-cheat-sheet).
- **Organization settings.** Set Copilot policies across the enterprise and its organizations, turn on code review policies, control which features work in IDEs and on GitHub.com, search the audit log for Copilot events, and manage seats with the REST API. Docs: [policies](https://docs.github.com/en/copilot/concepts/enterprise/policies), [organization policies](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-organization/manage-policies), [audit logs](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-enterprise/review-audit-logs), [user management REST API](https://docs.github.com/en/rest/copilot/copilot-user-management).

### Understand GitHub Copilot data and architecture

- **Data flow.** Follow a prompt from the editor to the model and back: context gathering and prompt building, the proxy, content filters, the model, and post-processing before a suggestion is shown. Know what data is used, where it goes, and who can use it for training. Docs: [prompt process flow](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/3-github-copilot-user-prompt-process-flow/), [Copilot data](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/4-github-copilot-data/), [model training settings](https://docs.github.com/en/copilot/how-tos/manage-your-account/manage-policies), [Copilot Trust Center](https://copilot.github.trust.page/).
- **Lifecycle and limits.** Describe how a suggestion is produced, filtered, shown, and accepted or rejected, and where large language models fall short. Docs: [inline suggestions application card](https://docs.github.com/en/copilot/responsible-use/inline-suggestions), [Copilot LLMs](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/5-github-copilot-large-language-models/).

### Apply prompt engineering and context crafting

- **Prompt structure and context.** Know what goes into a prompt besides your words (open files, selection, attachments, instructions, chat history), and use zero-shot, one-shot, and few-shot prompting on purpose. Docs: [prompt engineering for Copilot](https://docs.github.com/en/copilot/concepts/prompting-and-context/prompt-engineering), [prompt engineering foundations](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/2-prompt-engineering-foundations-best-practices/).
- **Prompting for better results.** Start general, then add requirements; give examples; split large tasks; remove ambiguity; and start a new conversation when history stops helping. Docs: [prompt engineering for Copilot](https://docs.github.com/en/copilot/concepts/prompting-and-context/prompt-engineering).

### Improve developer productivity with GitHub Copilot

- **Code quality and speed.** Generate, refactor, and document code; learn an unfamiliar language or codebase without leaving the editor; produce sample data; and modernize legacy code. Docs: [developer use cases module](https://learn.microsoft.com/en-us/training/modules/developer-use-cases-for-ai-with-github-copilot/).
- **Testing and security.** Write unit and integration tests, find edge cases and assertions, and ask for security and performance improvements. Docs: [unit tests with Copilot](https://learn.microsoft.com/en-us/training/modules/develop-unit-tests-using-github-copilot-tools/), [Chat cheat sheet](https://docs.github.com/en/copilot/reference/chat-cheat-sheet).

### Configure privacy, content exclusions, and safeguards

- **Privacy and exclusions.** Configure content exclusions and editor settings, and know who owns Copilot's output and where its limits are. Docs: [content exclusion](https://docs.github.com/en/copilot/concepts/security-governance-and-network-settings/content-exclusion), [exclude content](https://docs.github.com/en/copilot/how-tos/configure-content-exclusion/exclude-content-from-copilot).
- **Safeguards and troubleshooting.** Block suggestions that match public code, read code references when matching is allowed, and fix problems with suggestions and exclusions. Docs: [suggestions matching public code](https://docs.github.com/en/copilot/how-tos/manage-your-account/manage-policies), [find matching code](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/copilot-for-common-tasks/find-matching-code), [troubleshoot common issues](https://docs.github.com/en/copilot/how-tos/troubleshoot-copilot/troubleshoot-common-issues).

## Study plan

About 30 hours over four weeks. Use Copilot Free, Copilot Student, or a paid plan in VS Code for the practical tasks. Policies, organization custom instructions, and content exclusion need a Copilot Business or Copilot Enterprise organization; if you do not have one, study those pages closely and draw the settings out.

| Week | Focus | Tasks | Hours |
| --- | --- | --- | --- |
| 1 | Responsible use and the IDE | Read the study guide and the inline suggestions application card. Install Copilot in VS Code. Use `/explain`, `/fix`, and `/tests` on a small project, and try `#file` and `#selection`. Complete the first three modules of GitHub Copilot Fundamentals Part 1. | 7 |
| 2 | Prompts, context, and data | Write the same function three times with zero, one, and several examples and compare. Add `.github/copilot-instructions.md`, one path-specific `.instructions.md` file with `applyTo`, and one prompt file. Read the prompt process flow and Copilot data units, then sketch the flow from memory. | 7 |
| 3 | Agents, CLI, and GitHub features | Run agent mode on a multistep change. Install Copilot CLI, run one interactive session and one `copilot -p` command with `--allow-tool`, and try plan mode. Create a Copilot Space. Read the cloud agent risks page and the code review concept page; if your plan allows, assign an issue to Copilot and request a Copilot review. | 8 |
| 4 | Admin, privacy, and review | Read the policy pages for enterprises and organizations, write one content exclusion block for a repository and one for an organization, and list the audit log and REST API calls you would use. Set "Suggestions matching public code" in your own settings. Take the free practice assessment and reread the cheat sheet for weak domains. | 8 |

## Cheat sheet

### Plans

| Plan | Price | GitHub AI Credits each month | For |
| --- | --- | --- | --- |
| Copilot Free | Free | An allowance; inline suggestions capped at 2,000 completions | Individuals without Copilot from an organization or enterprise |
| Copilot Student | Free | An allowance | Verified students |
| Copilot Pro | $10 USD a month | 1,000 base + 500 flex = 1,500 | Individuals; free for some verified teachers and maintainers of popular open source projects |
| Copilot Pro+ | $39 USD a month | 3,900 base + 3,100 flex = 7,000 | Individuals who want premium models |
| Copilot Max | $100 USD a month | 10,000 base + 10,000 flex = 20,000 | Individuals with heavy, sustained use |
| Copilot Business | $19 USD per granted seat a month | 1,900 per user, pooled | Organizations and enterprises |
| Copilot Enterprise | $39 USD per granted seat a month | 3,900 per user, pooled | Enterprises on GitHub Enterprise Cloud |

- Business and Enterprise credits go into a shared enterprise pool; usage beyond it costs $0.01 USD per credit. Code completions and next edit suggestions are not billed in credits and are unlimited on paid plans.
- Free and Student get auto model selection only. Every plan includes Copilot CLI and the GitHub Copilot app. Copilot is not available on GitHub Enterprise Server.

Docs: [Plans for GitHub Copilot](https://docs.github.com/en/copilot/get-started/plans), checked October 28, 2026. Prices and allowances change often; the exam favors what each plan can do over what it costs.

| Feature | Free | Student | Pro | Pro+ | Max | Business | Enterprise |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Agent mode and MCP | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Copilot cloud agent | No | Yes | Yes | Yes | Yes | Yes | Yes |
| Copilot code review | "Review selection" in VS Code only | Yes | Yes | Yes | Yes | Yes | Yes |
| Third-party agents (preview) | No | No | Yes | Yes | Yes | Yes | Yes |
| Pull request summaries | No | Yes | Yes | Yes | Yes | Yes | Yes |
| Repository and personal custom instructions, prompt files | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Organization custom instructions | No | No | No | No | No | Yes | Yes |
| Block suggestions matching public code | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Content exclusion | No | No | No | No | No | Yes | Yes |
| Organization-wide policy management | No | No | No | No | No | Yes | Yes |
| Audit logs | No | No | No | Yes | Yes | Yes | Yes |
| GitHub Spark (preview) | No | No | No | Yes | No | No | Yes |

Docs: [Plans for GitHub Copilot](https://docs.github.com/en/copilot/get-started/plans).

### Features and settings

| Customization | Where it lives | What to remember |
| --- | --- | --- |
| Personal instructions | Your Copilot settings on GitHub.com | Apply to Copilot Chat on GitHub; Copilot CLI reads local files instead |
| Repository-wide instructions | `.github/copilot-instructions.md` | Sent with every request in the repository's context |
| Path-specific instructions | `.github/instructions/NAME.instructions.md` | `applyTo` glob in the frontmatter; `excludeAgent: "code-review"` or `"cloud-agent"` keeps one agent from using the file |
| Agent instructions | `AGENTS.md`, `CLAUDE.md`, or `GEMINI.md` | Not every feature reads them |
| Organization instructions | Organization settings, Business or Enterprise only | Used by Chat, code review, and cloud agent on GitHub.com, for every member of the organization |
| Prompt files | `.github/prompts/NAME.prompt.md` | Run on demand in VS Code, Visual Studio, JetBrains IDEs, and Xcode |

On Copilot Chat on GitHub.com, precedence runs from personal, to path-specific, to repository-wide, to agent instructions, to organization instructions. Most other surfaces combine the files with no precedence order. Code review reads instructions from the pull request's head branch. Docs: [custom instructions](https://docs.github.com/en/copilot/concepts/prompting-and-context/custom-instructions), [repository instructions](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/add-custom-instructions/add-repository-instructions), [prompt files](https://docs.github.com/en/copilot/concepts/prompting-and-context/prompt-files).

| Copilot CLI task | How |
| --- | --- |
| Install | `npm install -g @github/copilot` (Node.js 22 or later), `winget install GitHub.Copilot`, `brew install --cask copilot-cli`, or the install script |
| Start a session | `copilot`, then `/login` if you are not signed in |
| Sign in with a token | A fine-grained personal access token with the Copilot Requests permission in `COPILOT_GITHUB_TOKEN`, `GH_TOKEN`, or `GITHUB_TOKEN` |
| Run one prompt and exit | `copilot -p "your prompt"` |
| Plan before coding | Press Shift+Tab to switch to plan mode |
| Change the model | `/model` or `--model` |
| Approve tools ahead of time | `--allow-tool='shell(git)'`, `--allow-all-tools`; `--deny-tool` wins over both |
| Contain the agent | `/sandbox enable` for a local sandbox; `copilot --cloud` for a cloud sandbox (preview) |

Copilot CLI asks you to trust the directory you launch it from, and an organization or enterprise policy can turn it off for licensed users. Docs: [about Copilot CLI](https://docs.github.com/en/copilot/concepts/copilot-surfaces/copilot-cli), [install](https://docs.github.com/en/copilot/how-tos/copilot-cli/set-up-copilot-cli/install-copilot-cli).

| Copilot Chat in VS Code | Examples |
| --- | --- |
| Slash commands | `/explain`, `/fix`, `/tests`, `/fixTestFailure`, `/new`, `/clear`, `/help` (Visual Studio adds `/doc` and `/optimize`) |
| Chat variables | `#file`, `#selection`, `#function`, `#class`, `#block`, `#project` |
| Chat participants | `@github`, `@terminal`, `@vscode`, `@azure` (preview) |

Docs: [Chat cheat sheet](https://docs.github.com/en/copilot/reference/chat-cheat-sheet). Agent mode is available in VS Code, Visual Studio, JetBrains IDEs, Eclipse, and Xcode; edit mode in VS Code and JetBrains IDEs. ([Feature matrix](https://docs.github.com/en/copilot/reference/copilot-feature-matrix))

Copilot cloud agent guardrails ([docs](https://docs.github.com/en/copilot/concepts/security-governance-and-network-settings/risks-and-mitigations)):

- Only people with write access can start it, and it never sees comments from people without write access.
- It pushes to one branch only: a new `copilot/` branch, or the existing pull request's branch when you mention `@copilot` on that pull request.
- It cannot mark its pull request ready for review, approve it, or merge it, and the person who asked for the pull request cannot approve it.
- By default, GitHub Actions workflows do not run on its pull requests until someone with write access selects **Approve and run workflows**.
- Its internet access goes through a firewall, and each of its commits links to the session log.

Copilot code review ([docs](https://docs.github.com/en/copilot/concepts/agent-capabilities/agent-powered-workflows-and-operations/code-review)):

- Copilot reviews a pull request when you request it. Users on Pro, Pro+, Max, Business, or Enterprise can set automatic reviews of their own pull requests (not available to managed user accounts), and repository and organization owners can set automatic reviews with rulesets.
- It reviews once unless "Review new pushes" is on; otherwise request the review again after new commits.
- By default its reviews do not count toward required approvals. You cannot switch its model.
- Organizations on Business or Enterprise can let members without a Copilot license use it on GitHub.com by enabling AI credits paid usage and the policy for members without a license.

Copilot Spaces ([docs](https://docs.github.com/en/copilot/concepts/prompting-and-context/spaces)): anyone with a Copilot license, including Free, can create one. Spaces hold repositories, files, pull requests, issues, notes, and uploads; GitHub sources stay in sync as they change. Use them in Copilot Chat on GitHub, or in the IDE through the GitHub MCP server.

### Organization management

| Policy rule | Behavior |
| --- | --- |
| Order | The enterprise sets each policy first: enabled, disabled, or let organizations decide. An organization cannot override an enterprise choice. |
| Cloud agent | The enterprise picks exactly which organizations get it. |
| Seats from several organizations in one enterprise | The least restrictive setting usually applies. |
| Seats from several enterprises | The most restrictive setting almost always applies. |
| Users licensed directly by the enterprise | A separate setting decides whether "let organizations decide" policies default to on or off for them. |
| Personal plans | Cancelled when the user gets a Business or Enterprise seat, so they never conflict. |
| Client policies | Copilot CLI and the GitHub Copilot app have separate policies; you can allow one and not the other. |

Docs: [Copilot policies](https://docs.github.com/en/copilot/concepts/enterprise/policies), [organization policies](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-organization/manage-policies). In organization settings, **Copilot > Policies** holds feature and privacy policies and **Copilot > Models** holds model availability. On Business or Enterprise, enabling Copilot in GitHub.com also shows options to opt in to preview features and user feedback.

| Seat task (REST API) | Endpoint |
| --- | --- |
| Seat summary and settings | `GET /orgs/{org}/copilot/billing` |
| List seat assignments | `GET /orgs/{org}/copilot/billing/seats` |
| Add or remove users | `POST` or `DELETE /orgs/{org}/copilot/billing/selected_users` |
| Add or remove teams | `POST` or `DELETE /orgs/{org}/copilot/billing/selected_teams` |
| One member's seat | `GET /orgs/{org}/members/{username}/copilot` |

Classic tokens need `manage_billing:copilot`, or `read:org` for reads and `admin:org` for changes. Removed users keep access until the end of the billing cycle unless a team still grants it; unassigning a license at the enterprise level revokes access immediately. Docs: [user management REST API](https://docs.github.com/en/rest/copilot/copilot-user-management), [revoke access](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-organization/manage-access/revoke-access).

Audit log ([docs](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-enterprise/review-audit-logs)): search `action:copilot` for plan, policy, and license changes, and `actor:Copilot` for agent activity. Events are kept for 180 days; stream to a SIEM for longer. Prompts that users send from their own machines are not in the audit log.

### Data and architecture

Prompt flow ([Microsoft Learn unit](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/3-github-copilot-user-prompt-process-flow/)):

1. The client gathers context (code before and after the cursor, the file name and type, open tabs, project structure, and languages), builds the prompt, and sends it over HTTPS.
2. A proxy in an Azure tenant owned by GitHub filters the traffic and blocks attempts to manipulate the prompt.
3. Filters screen out offensive content and personal data.
4. The model generates suggestions.
5. Post-processing filters the output again, checks code quality for flaws such as SQL injection, and, if enabled, drops suggestions that match public code. Output that fails is truncated or discarded.
6. Only what passes reaches you, and your accept or reject choice feeds back into the loop.

- Copilot Business and Copilot Enterprise data is not used to train GitHub's models. Since April 24, 2026, GitHub may use interactions from Copilot Free, Pro, Pro+, and Max to train models unless the user turns that off in Copilot settings. ([Docs](https://docs.github.com/en/copilot/how-tos/manage-your-account/manage-policies))
- The user, not GitHub, carries the risk of generated code: security flaws, bugs, and IP infringement. ([Docs](https://docs.github.com/en/copilot/responsible-use/inline-suggestions))

### Privacy and safeguards

- **Content exclusion** is on Business and Enterprise only. Repository admins exclude paths in their repository for every Copilot user in the enterprise; organization owners exclude for users who get a seat from that organization; enterprise owners exclude for all Copilot users in the enterprise.
- Excluded files get no inline suggestions, do not inform suggestions in other files or chat answers, and are skipped by Copilot code review.
- Repository syntax is a list such as `- "/scripts/**"`. Organization and enterprise syntax keys each path list by a repository reference, or by `"*"` to match any repository and files outside Git. Patterns use fnmatch and ignore case.
- Changes can take up to 30 minutes to reach an IDE. Reload the window in VS Code or restart Visual Studio and JetBrains IDEs to apply them sooner; Vim and Neovim fetch them on each file open.
- Limits: the IDE can still pass semantic details from an excluded file, such as types and hover definitions; symbolic links and remote filesystems are not covered; and exclusion is not supported in edit and agent modes of Copilot Chat in VS Code and other editors.

Docs: [content exclusion](https://docs.github.com/en/copilot/concepts/security-governance-and-network-settings/content-exclusion), [exclude content](https://docs.github.com/en/copilot/how-tos/configure-content-exclusion/exclude-content-from-copilot).

- **Suggestions matching public code.** With Block, Copilot compares each suggestion plus about 150 characters of surrounding code with public code on GitHub and hides matches and near matches. With Allow, it shows code references with the license and the repository link. Users with a seat from an organization inherit the organization's setting. ([Policies](https://docs.github.com/en/copilot/how-tos/manage-your-account/manage-policies), [find matching code](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/copilot-for-common-tasks/find-matching-code))
- **Web search** for Copilot Chat uses Bing and is off by default in personal settings. ([Docs](https://docs.github.com/en/copilot/how-tos/manage-your-account/manage-policies))

## Free official resources

- [Microsoft Learn certification page](https://learn.microsoft.com/en-us/credentials/certifications/github-copilot/): exam details, scheduling, price for your country, and the recertification note.
- [GH-300 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/gh-300): the full skills outline and change log.
- [GitHub Learn credentials](https://learn.github.com/credentials): GitHub's certification list and exam FAQ.
- Learning paths: [GitHub Copilot Fundamentals Part 1 of 2](https://learn.microsoft.com/en-us/training/paths/copilot/) and [Part 2 of 2](https://learn.microsoft.com/en-us/training/paths/gh-copilot-2/), also bundled as [course GH-300T00](https://learn.microsoft.com/en-us/training/courses/gh-300t00).
- [Free practice assessment](https://aiskillsnavigator.microsoft.com/credentials/cert-4c64d19db13165eac18cad5752c633df55b338447ba755c04781b777c36a796d): on AI Skills Navigator; you need to sign in.
- [GitHub exam sandbox](https://GHCertDemo.starttest.com): try the exam interface before test day.
- [GitHub Copilot documentation](https://docs.github.com/en/copilot) and the [Copilot Trust Center](https://copilot.github.trust.page/).
- To practice: [Copilot Free](https://github.com/features/copilot/plans) for individuals, and [Copilot Student](https://docs.github.com/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot/set-up-for-students) for verified students.

## Practice questions

[practice-questions.md](practice-questions.md) has 15 original scenario questions across all six domains, each with the answer, why the other options are wrong, and a link to the docs. For more, the [Examice GH-300 practice bank](https://examice.com/exams/microsoft/gh-300?utm_source=github&utm_medium=social&utm_campaign=gh-300-study-guide-and-practice-questions&utm_content=link_2) has 120+ questions with a written explanation and a discussion under each, and the first 5 are free.

## Exam day tips

- You get 100 minutes for 60 scored questions plus 10–15 unscored ones, a little over 1 minute each. Flag long questions and come back to them.
- The exam is closed book. Microsoft Learn, which role exams allow, is not available on GitHub exams.
- Read for the plan in the question. "Business or Enterprise" often decides the answer for content exclusion, policies, and organization instructions.
- Read for the surface too. An answer that is right for VS Code chat can be wrong for agent mode, Copilot CLI, or GitHub.com.
- Wrong answers cost nothing and some questions are unscored, so answer everything. ([Scoring](https://learn.microsoft.com/en-us/credentials/certifications/exam-scoring-reports))
- Try the [GitHub exam sandbox](https://GHCertDemo.starttest.com) beforehand, and register with a personal Microsoft account so the record stays with you.

## FAQ

**How hard is GH-300?**
Microsoft rates it Intermediate. The audience profile expects you to know GitHub basics and at least one programming language, and the outline goes beyond the editor into data handling, policies, and content exclusion. You need a scaled 700 to pass. ([Study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/gh-300))

**How long should I study for GH-300?**
Neither GitHub nor Microsoft publishes a study time. The plan in this guide takes about 30 hours over four weeks, assuming you already use GitHub daily.

**Does the GitHub Copilot certification expire?**
GitHub certifications are valid for 2 years. GitHub is moving them to Microsoft's recertification process, which will let you renew with an unproctored assessment on Microsoft Learn instead of the full exam. Until then, certifications that expire before the new process is ready are extended by 6 months, and holders of an expired certification can ask learn@github.com for one exam voucher. ([GitHub Learn FAQ](https://learn.github.com/credentials), [certification page](https://learn.microsoft.com/en-us/credentials/certifications/github-copilot/))

**What is the GH-300 retake policy?**
Wait 24 hours after the first failed attempt and 14 days before each later attempt, with at most 5 attempts a year. ([GitHub Learn FAQ](https://learn.github.com/credentials), [retake policy](https://learn.microsoft.com/en-us/credentials/support/retake-policy))

**Is GH-300 a GitHub exam or a Microsoft exam?**
It is a GitHub certification. GitHub lists it on GitHub Learn, and Microsoft Learn hosts its exam page, study guide, and Pearson VUE scheduling under the code GH-300. ([Certification page](https://learn.microsoft.com/en-us/credentials/certifications/github-copilot/), [GitHub Learn](https://learn.github.com/credentials))

**What changed in the August 7, 2026 update?**
The change log marks minor changes to three sections: Copilot in the IDE, Copilot features and capabilities, and safeguards and troubleshooting. ([Study guide change log](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/gh-300))

## Contributing

Copilot plans and features change often. If a plan, setting, or file path here no longer matches the docs, open an issue or a pull request with a link to the GitHub doc that shows the current behavior.

## License

Text and questions © Examice, licensed under CC BY 4.0. See [LICENSE](LICENSE).

GitHub and GitHub Copilot are trademarks of GitHub, Inc. Microsoft is a trademark of the Microsoft group of companies. This repository is not affiliated with or endorsed by GitHub or Microsoft.
