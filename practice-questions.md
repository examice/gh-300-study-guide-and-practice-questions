# GH-300 practice questions

These 15 scenario questions cover the six GH-300 domains in proportion to their weights in the [official study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/gh-300) (skills measured as of August 7, 2026). They stick to documented behavior that changes rarely; plan prices and allowances are left to the [README](README.md) cheat sheet. Each answer explains why the right option works, why the others fail, and links to the GitHub or Microsoft Learn page behind it.

> Unofficial study notes by Examice. Not affiliated with or endorsed by GitHub or Microsoft. The practice questions are original and are not taken from the exam.

### Question 1

*Domain: Use GitHub Copilot responsibly*

Copilot wrote a function that parses uploaded CSV files, and it passed one manual test. A teammate wants to merge it today because "Copilot already filters out bad code." What should the team do?

- A. Merge it, because Copilot's post-processing removes insecure code before showing a suggestion.
- B. Turn on blocking of suggestions that match public code, which confirms the function is correct.
- C. Treat it like any other code: review it, add tests for edge cases and malformed input, and run the usual security checks before merging.
- D. Merge it, because GitHub takes responsibility for bugs in code that Copilot generates.

<details><summary>Show answer</summary>

**C.** GitHub's guidance is to review, test, and validate every suggestion, and to follow secure coding and code review practices. The user, not GitHub, carries the risk of generated code: security flaws, bugs, and IP infringement.

- A is wrong because the filters reduce risk but do not guarantee secure or correct code.
- B is wrong because the public code filter only hides suggestions that match public code. It says nothing about correctness.
- D is wrong because the user, not GitHub, owns the risk of generated code.

Docs: [Application card: inline suggestions](https://docs.github.com/en/copilot/responsible-use/inline-suggestions)

</details>

### Question 2

*Domain: Use GitHub Copilot responsibly*

A team maintains a codebase in a language that is rare in public repositories. Copilot's suggestions are noticeably worse for this code than for the team's JavaScript services. What explains the difference?

- A. Content exclusion is turned on for that language.
- B. Suggestion quality depends on how much varied code in that language the model saw in training, and rare languages are less represented.
- C. Copilot only produces suggestions for a fixed list of five languages.
- D. Blocking suggestions that match public code turns off suggestions for rare languages.

<details><summary>Show answer</summary>

**B.** GitHub lists limited scope as a known limitation: quality varies with the volume and diversity of training data for each language. JavaScript is well represented, so it is one of the best supported languages.

- A is wrong because content exclusion targets repositories and file paths, not languages.
- C is wrong because Copilot supports many languages; quality varies, but support is not limited to a short list.
- D is wrong because the public code filter hides matching suggestions. It does not switch off a language.

Docs: [Application card: inline suggestions](https://docs.github.com/en/copilot/responsible-use/inline-suggestions)

</details>

### Question 3

*Domain: Use GitHub Copilot responsibly*

An insurance company wants to use Copilot to help write the rules that decide whether a claim is approved. Which guidance applies most directly?

- A. Turn on web search for Copilot Chat so the rules are always accurate.
- B. Use few-shot prompts, which guarantee correct rules.
- C. None, because Copilot refuses tasks in regulated industries.
- D. Take extra care with consequential decisions in sensitive domains: keep human oversight, evaluate outcomes, and make sure affected people can understand and appeal decisions.

<details><summary>Show answer</summary>

**D.** GitHub's best practices call out consequential decisions, such as access to insurance or healthcare, as needing particular caution, human oversight, and a way for stakeholders to understand and appeal outcomes. Legal and regulatory obligations also need evaluation.

- A is wrong because web search adds information but does not make generated logic correct or fair.
- B is wrong because examples improve results but no prompt technique guarantees correctness.
- C is wrong because GitHub's guidance expects Copilot to be used in sensitive domains and asks you to take care there. It does not describe refusing whole industries.

Docs: [Application card: inline suggestions](https://docs.github.com/en/copilot/responsible-use/inline-suggestions), [Responsible AI with GitHub Copilot](https://learn.microsoft.com/en-us/training/modules/responsible-ai-with-github-copilot/)

</details>

### Question 4

*Domain: Use GitHub Copilot features*

You want a nightly script to run Copilot CLI with one prompt. Copilot may run any `git` command without asking, but it must never run `git push`. Which command fits?

- A. `copilot -p "Summarize today's commits" --allow-tool='shell(git)' --deny-tool='shell(git push)'`
- B. `copilot -p "Summarize today's commits" --allow-all-tools`
- C. `copilot -p "Summarize today's commits" --allow-tool='shell(git push)'`
- D. `copilot -p "Summarize today's commits" --deny-tool='shell(git)' --allow-tool='shell(git push)'`

<details><summary>Show answer</summary>

**A.** `-p` runs a single prompt and exits. `--allow-tool='shell(git)'` approves `git` commands, and `--deny-tool` takes precedence over `--allow-tool` and `--allow-all-tools`, so `git push` stays blocked.

- B is wrong because `--allow-all-tools` lets Copilot run any command you could run, including `git push`.
- C is wrong because it allows the one command that must be blocked.
- D is wrong because it blocks every `git` command, and the deny rule wins over the narrower allow rule.

Docs: [About GitHub Copilot CLI](https://docs.github.com/en/copilot/concepts/copilot-surfaces/copilot-cli)

</details>

### Question 5

*Domain: Use GitHub Copilot features*

Your enterprise owner set a Copilot feature policy to Disabled at the enterprise level. The owner of one organization in the enterprise wants the feature turned on for their developers only. What has to happen?

- A. The organization owner enables the policy in the organization settings, which overrides the enterprise.
- B. Each developer enables the feature in their personal Copilot settings.
- C. The enterprise owner must change the policy to Enabled or to let organizations decide. The organization owner cannot override the enterprise setting.
- D. The organization owner opts in to preview features, which overrides disabled policies.

<details><summary>Show answer</summary>

**C.** The enterprise level decides first. When the enterprise has chosen a specific setting, such as disabling a feature everywhere, an organization cannot override it. Only "let organizations decide" hands the choice to organization owners.

- A is wrong because organization settings cannot override an explicit enterprise choice.
- B is wrong because users with a Business or Enterprise seat are governed by the policies of the enterprise or organization that licenses them.
- D is wrong because the preview opt-in only controls access to features that are not yet generally available. It does not override policies.

Docs: [Copilot policies](https://docs.github.com/en/copilot/concepts/enterprise/policies), [managing policies in your organization](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-organization/manage-policies)

</details>

### Question 6

*Domain: Use GitHub Copilot features*

An organization on Copilot Business adds organization custom instructions that tell Copilot to link to the internal security wiki for security questions. On GitHub.com the instructions work, but developers say Copilot Chat in VS Code ignores them. Why?

- A. Organization custom instructions require Copilot Enterprise.
- B. Organization custom instructions reach only three features, all on GitHub.com: Copilot Chat, Copilot code review, and Copilot cloud agent.
- C. Each developer must accept the organization instructions in their personal settings.
- D. Personal instructions always override organization instructions in VS Code.

<details><summary>Show answer</summary>

**B.** GitHub documents that organization custom instructions apply only on GitHub.com, to Copilot Chat, Copilot code review, and Copilot cloud agent. For the IDE, put shared guidance in repository instructions such as `.github/copilot-instructions.md`.

- A is wrong because organization custom instructions are available on Copilot Business and Copilot Enterprise.
- C is wrong because there is no acceptance step; organization instructions apply to all members on the supported surfaces.
- D is wrong because VS Code combines applicable instruction files without a general precedence order, and organization instructions do not reach the IDE at all.

Docs: [Custom instructions](https://docs.github.com/en/copilot/concepts/prompting-and-context/custom-instructions)

</details>

### Question 7

*Domain: Use GitHub Copilot features*

The security team asks for two things: who changed a Copilot policy in the enterprise last month, and the prompts developers typed into Copilot Chat in their IDEs that week. What can the enterprise audit log give them?

- A. Both, filtered with `actor:Copilot`.
- B. Neither, because Copilot events are only in the organization billing report.
- C. Both, as long as the events are less than 2 years old.
- D. The policy change, found with `action:copilot`, but not the prompts, which the audit log does not record.

<details><summary>Show answer</summary>

**D.** The audit log records changes to Copilot settings, policies, and licenses (search `action:copilot`) and agent activity on GitHub (search `actor:Copilot`). It does not include client session data such as prompts sent from a user's machine; capturing those needs a custom solution. Events are kept for 180 days.

- A is wrong because `actor:Copilot` shows what Copilot agents did on GitHub, not prompts typed in an IDE.
- B is wrong because Copilot events are in the audit log.
- C is wrong because the audit log keeps 180 days of events and never held IDE prompts.

Docs: [Reviewing audit logs for Copilot](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-enterprise/review-audit-logs)

</details>

### Question 8

*Domain: Understand GitHub Copilot data and architecture*

Your organization blocks suggestions that match public code. In the Copilot request flow, where is a matching suggestion stopped?

- A. In post-processing, after the model generates the suggestion and before it is shown to you.
- B. In the editor, after you accept the suggestion.
- C. During context gathering, before the prompt is built.
- D. During model training, so matching code can never be generated.

<details><summary>Show answer</summary>

**A.** On the way back from the model, Copilot filters and checks the output. When blocking is on, a suggestion that matches public code, compared with about 150 characters of surrounding code, is dropped or truncated, so you never see it.

- B is wrong because the check runs before the suggestion is shown, not after acceptance.
- C is wrong because context gathering builds the prompt; there is no suggestion yet to compare.
- D is wrong because the filter works on each generated suggestion. GitHub says Copilot can still produce matches with low probability, which is why the filter exists.

Docs: [Prompt process flow](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/3-github-copilot-user-prompt-process-flow/), [suggestions matching public code](https://docs.github.com/en/copilot/how-tos/manage-your-account/manage-policies)

</details>

### Question 9

*Domain: Understand GitHub Copilot data and architecture*

Your company uses Copilot Business. Legal asks whether code in developers' prompts is used to train GitHub's AI models, and where developers turn that off. What is the answer?

- A. Each developer must set "Allow GitHub to use my data for AI model training" to Disabled.
- B. The organization owner must add every repository to content exclusion to stop training.
- C. GitHub does not use Copilot Business data to train models; the Data Protection Agreement prohibits it, so the training setting is not even shown to Business users.
- D. Data is used for training unless the enterprise owner opts out in the AI controls tab.

<details><summary>Show answer</summary>

**C.** Copilot Business and Copilot Enterprise data is not used to train GitHub's models; the Data Protection Agreement rules that out. The training setting appears only for individual plans, which is why a Business user cannot find it.

- A is wrong because that setting is not displayed for accounts with a Business or Enterprise license.
- B is wrong because content exclusion controls what Copilot can read for suggestions and answers. It is not a training control.
- D is wrong because there is no training to opt out of for Business data.

Docs: [Managing Copilot policies as an individual subscriber](https://docs.github.com/en/copilot/how-tos/manage-your-account/manage-policies), [Copilot Trust Center](https://copilot.github.trust.page/)

</details>

### Question 10

*Domain: Apply prompt engineering and context crafting*

You ask Copilot Chat for a function that extracts dates from free text. Your logs use four date formats, and the first answer handles only two of them. What change to the prompt is most likely to fix this?

- A. Send the same prompt again and hope for a better answer.
- B. List each of the four formats with a sample input and the expected output.
- C. Shorten the prompt by removing the list of requirements.
- D. Move the most important requirement to the middle of the prompt.

<details><summary>Show answer</summary>

**B.** Giving examples, also called few-shot prompting, shows Copilot the exact patterns you need. GitHub's prompt guidance uses this case: list the formats and show sample input and output.

- A is wrong because rerunning without new information is not a strategy; the prompt still lacks the missing formats.
- C is wrong because removing requirements gives Copilot less to work with.
- D is wrong because Copilot weighs the start and end of a prompt most heavily, so the middle is the weakest spot.

Docs: [Prompt engineering for Copilot](https://docs.github.com/en/copilot/concepts/prompting-and-context/prompt-engineering), [prompt engineering foundations](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/2-prompt-engineering-foundations-best-practices/)

</details>

### Question 11

*Domain: Apply prompt engineering and context crafting*

After a long Copilot Chat conversation about a payment service, you ask an unrelated question about a CSS layout. The answers keep referring to the payment code. What should you do?

- A. Add "ignore everything above" to the end of your question.
- B. Switch to a different model in the same conversation.
- C. Open more files from the payment service.
- D. Start a new conversation for the new task.

<details><summary>Show answer</summary>

**D.** Copilot uses conversation history as context. GitHub recommends starting a new conversation or session when you begin a new task so only relevant history is sent.

- A is wrong because the earlier messages are still part of the context; a fresh conversation removes them.
- B is wrong because changing the model does not change the history being sent.
- C is wrong because it adds more unrelated context, the opposite of what you need.

Docs: [Prompt engineering for Copilot](https://docs.github.com/en/copilot/concepts/prompting-and-context/prompt-engineering)

</details>

### Question 12

*Domain: Improve developer productivity with GitHub Copilot*

In VS Code you want Copilot Chat to write unit tests for one function, including cases for empty input and very large numbers. What is the most direct approach?

- A. Select the function and use `/fix`.
- B. Use `/new` to start a test project.
- C. Select the function, use `/tests`, and name the edge cases you want covered in the same prompt.
- D. Use `/explain`, then paste the explanation into a test file.

<details><summary>Show answer</summary>

**C.** `/tests` generates unit tests for the selected code, and naming edge cases in the prompt tells Copilot which assertions you expect.

- A is wrong because `/fix` proposes fixes for problems in the selected code.
- B is wrong because `/new` creates a new project, not tests for existing code.
- D is wrong because an explanation is not a test.

Docs: [Copilot Chat cheat sheet](https://docs.github.com/en/copilot/reference/chat-cheat-sheet), [develop unit tests with Copilot](https://learn.microsoft.com/en-us/training/modules/develop-unit-tests-using-github-copilot-tools/)

</details>

### Question 13

*Domain: Improve developer productivity with GitHub Copilot*

You inherit a large legacy module with no tests and must modernize it with Copilot's help. Which approach follows GitHub's guidance?

- A. Ask Copilot to explain the module, generate tests that capture its current behavior, then refactor in small steps and run the tests after each one.
- B. Ask Copilot to rewrite the whole module in a single prompt.
- C. Refactor first, then ask Copilot to write tests that match the new code.
- D. Skip tests, because Copilot checks generated code for bugs before showing it.

<details><summary>Show answer</summary>

**A.** GitHub recommends breaking complex tasks into smaller ones and notes that unit tests can serve as examples of the behavior you want. Tests written before the refactor tell you whether anything changed.

- B is wrong because one large request is the kind of complex task GitHub advises splitting up.
- C is wrong because tests written after the refactor describe the new code, so they cannot show whether behavior changed.
- D is wrong because Copilot's checks reduce some risks but do not replace testing.

Docs: [Prompt engineering for Copilot](https://docs.github.com/en/copilot/concepts/prompting-and-context/prompt-engineering), [developer use cases for AI](https://learn.microsoft.com/en-us/training/modules/developer-use-cases-for-ai-with-github-copilot/)

</details>

### Question 14

*Domain: Configure privacy, content exclusions, and safeguards*

Your enterprise on Copilot Business wants every Copilot user in the enterprise, whichever organization licenses them, to get no help from Copilot in any `.env` file, in any repository or outside Git. What should you configure?

- A. Content exclusion in each repository's settings, with `- ".env"`.
- B. A `.github/copilot-instructions.md` file in each repository that tells Copilot to ignore `.env` files.
- C. Content exclusion in one organization's settings, with `"*":` followed by `- "**/.env"`.
- D. Content exclusion in the enterprise's AI controls, with `"*":` followed by `- "**/.env"`.

<details><summary>Show answer</summary>

**D.** Enterprise rules cover every Copilot user in the enterprise. The `"*"` key matches any repository and files that are not under Git control, and `**/.env` matches the file at any depth.

- A is wrong because repository rules only cover that repository and cannot reach files outside Git.
- B is wrong because custom instructions guide responses but do not enforce a policy; excluded content is configured in settings.
- C is wrong because organization rules apply only to users who receive their seat from that organization.

Docs: [Excluding content from Copilot](https://docs.github.com/en/copilot/how-tos/configure-content-exclusion/exclude-content-from-copilot), [custom instructions](https://docs.github.com/en/copilot/concepts/prompting-and-context/custom-instructions)

</details>

### Question 15

*Domain: Configure privacy, content exclusions, and safeguards*

You added `/config/**` to a repository's content exclusion. Five minutes later a developer still gets inline suggestions in `/config/app.yaml` in VS Code, which was already open. What is the most likely cause and fix?

- A. Patterns are case sensitive, so the path must match the folder's exact case.
- B. Changes can take up to 30 minutes to reach an IDE that already loaded the settings; run **Developer: Reload Window** from the Command Palette.
- C. Content exclusion only works on Copilot Enterprise.
- D. Exclusions only apply after the developer clones the repository again.

<details><summary>Show answer</summary>

**B.** An IDE that already loaded the exclusion settings can take up to 30 minutes to pick up a change. In VS Code, reloading the window applies them right away. JetBrains IDEs and Visual Studio need a restart; Vim and Neovim fetch exclusions each time a file opens.

- A is wrong because content exclusion patterns are case insensitive.
- C is wrong because content exclusion is available on Copilot Business and Copilot Enterprise.
- D is wrong because the settings come from GitHub, not from the local clone.

Docs: [Excluding content from Copilot](https://docs.github.com/en/copilot/how-tos/configure-content-exclusion/exclude-content-from-copilot)

</details>

## More practice

The [Examice GH-300 practice bank](https://examice.com/exams/microsoft/gh-300?utm_source=github&utm_medium=social&utm_campaign=gh-300-study-guide-and-practice-questions&utm_content=link_3) has 120+ questions, each with a written explanation and a discussion. The first 5 are free.
