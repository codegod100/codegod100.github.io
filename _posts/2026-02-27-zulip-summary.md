---
published: true
date: 2026-02-27
title: Zulip Daily Summary (2026-02-27)
layout: post
categories: [zulip, summary]
---
# Roc Zulip Daily Summary — 2026-02-27

- **Realm:** https://roc.zulipchat.com
- **Window:** 2026-02-27 12:00 AM to 2026-02-28 12:00 AM (America/Los_Angeles)
- **Messages:** 40
- **LLM:** vertex_open_model model=zai-org/glm-5-maas topics=8 ok=8/8

## Top threads

### Help Wanted : migrating the Roc Examples

- **Channel:** contributing
- **Conversation:** Help Wanted : migrating the Roc Examples
- **Messages:** 15
- **People:** 6
- **Time:** 1:38 AM–6:34 PM (America/Los_Angeles)
- **Participants:** Luke Boswell, Anton, Richard Feldman, Tobias Steckenborn
- **Link:** <https://roc.zulipchat.com/#narrow/channel/316715-contributing/topic/Help.20Wanted.20.3A.20migrating.20the.20Roc.20Examples/near/576381244>

**Key links**

- <https://>
- <https://roc.zulipchat.com/#narrow/channel/316715-contributing/topic/Help.20Wanted.20.3A.20migrating.20the.20Roc.20Examples/near/576296585>
- <https://github.com/roc-lang/roc-playground>
- <https://roc-lang.github.io/roc-playground/#content=YXBwIFttYWluIV0geyBwZjogcGxhdGZvcm0gImh0dHBzOi8vZ2l0aHViLmNvbS9sdWtld2lsbGlhbWJvc3dlbGwvcm9jLXBsYXRmb3JtLXRlbXBsYXRlLXppZy9yZWxlYXNlcy9kb3dubG9hZC8wLjYvMkJmR240TTl1V0pOaERWZU1naEdlWE5WREZpak1mUHNtbVZlbzZNNFFqS1gudGFyLnpzdCIgfQoKaW1wb3J0IHBmLlN0ZG91dAoKbWFpbiEgPSB8X2FyZ3N8IHsKICAgIFN0ZG91dC5saW5lISgiSGVsbG8sIFdvcmxkISIpCiAgICBPayh7fSkKfQ==>
- <https://github.com/roc-lang/examples>

**Summary**

Contributors are coordinating the migration of Roc examples to a new compiler version, discussing technical limitations with the "echo" platform and the Roc playground, and setting up CI for the new examples branch.

**Key points**

- Norbert Hajagos volunteered to migrate examples alphabetically from the bottom up, reserving three specific examples, and will avoid using AI.
- Anton created a `new-compiler` branch in the examples repo for contributors to use as a base and add CI tests.
- A limitation was identified where `roc build` does not work for headerless apps (like those using the echo platform) because the CLI acts as the host; the team decided to implement an error message rather than support building.
- Tobias Steckenborn suggested improving the Roc playground by using a headless platform to allow console output and better samples.
- Luke Boswell clarified that the CLI refactoring for the playground was descopied from the initial PR to unblock migration but is now easier to wire up.

**Open questions**

- None.

**Action items**

- Norbert Hajagos to migrate examples starting from the bottom of the alphabet.
- Contributors to base PRs on the `new-compiler` branch and add tests to `ci_scripts/all_tests.sh`.
- Developers to implement an error message explaining that `roc build` only works on `app` modules.

### AI Workflow

- **Channel:** off topic
- **Conversation:** AI Workflow
- **Messages:** 11
- **People:** 4
- **Time:** 2:53 AM–6:20 AM (America/Los_Angeles)
- **Participants:** Niclas Ahden, Anton, Jared Ramirez, Luke Boswell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/306878-off-topic/topic/AI.20Workflow/near/576272503>

**Key links**

- <https://roc.zulipchat.com/#narrow/channel/306878-off-topic/topic/AI.20Workflow/near/576230987>
- <https://roc.zulipchat.com/#narrow/channel/306878-off-topic/topic/AI.20Workflow/near/576249418>
- <https://code.claude.com/docs/en/claude-code-on-the-web>
- <https://roc.zulipchat.com/#narrow/channel/306878-off-topic/topic/AI.20Workflow/near/576270628>
- <https://code.claude.com/docs/en/remote-control>

**Summary**

The thread discusses workflows for running multiple parallel Claude Code sessions, comparing directory isolation strategies and exploring the security implications of using `--dangerously-skip-permissions` within virtual machines.

**Key points**

- Users manage parallel sessions by creating multiple repository clones (e.g., `roc1` through `roc9`) or using git worktrees, often mapping them to virtual desktops.
- A proposed "ideal" workflow involves using Nix to manage lightweight VMs for total session isolation, enabling the use of `--dangerously-skip-permissions`.
- Significant security risks remain even inside a VM, such as access to local networks, production secrets, or the potential for illegal activity and crypto mining.
- Claude Code on the web was highlighted as a potential security improvement or alternative to local VM management.

**Open questions**

- None explicitly stated.

**Action items**

- None explicitly stated.

### Reassign or redeclare a constant?

- **Channel:** beginners
- **Conversation:** Reassign or redeclare a constant?
- **Messages:** 7
- **People:** 3
- **Time:** 11:51 AM–12:25 PM (America/Los_Angeles)
- **Participants:** Daren, Luke Boswell, Norbert Hajagos
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Reassign.20or.20redeclare.20a.20constant.3F/near/576343812>

**Key links**

- <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Reassign.20or.20redeclare.20a.20constant.3F/near/576341802>
- <https://i.postimg.cc/157gSz72/image.png>

**Summary**

Daren reported a discrepancy where the tutorial claimed constants cannot be redeclared, but the compiler only issued a warning and allowed the code to run. Contributors clarified that the compiler follows an "inform don't block" philosophy, though the resulting non-zero exit code is intended to prevent such warnings from passing CI.

**Key points**

- The tutorial states that redeclaring a constant causes a compile-time error, but Daren observed it only resulted in a warning and the program executed successfully.
- Luke Boswell explained that the design philosophy is "inform don't block," allowing execution to proceed despite the warning.
- While the application runs, the `roc` or `roc build` commands exit with a non-zero status code to prevent warnings from slipping through CI pipelines.

**Open questions**

- Luke Boswell noted uncertainty regarding the specific distinction between an Error and a Warning in the compiler's output.

**Action items**

- None mentioned.

### basic-dom

- **Channel:** ideas
- **Conversation:** basic-dom
- **Messages:** 3
- **People:** 2
- **Time:** 6:31 AM–12:04 PM (America/Los_Angeles)
- **Participants:** Ghislain, Luke Boswell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/304641-ideas/topic/basic-dom/near/576340892>

**Key links**

- <https://hacks.mozilla.org/wp-content/uploads/2026/02/Screenshot-2026-02-25-at-2.22.23-PM-1536x1018.png>
- <https://hacks.mozilla.org/2026/02/making-webassembly-a-first-class-language-on-the-web/>

**Summary**

Ghislain shared an article about WebAssembly becoming a first-class web language and suggested implementing the WebAssembly Component Model in Roc. Luke Boswell responded that he has a rough "basic-dom" platform for testing the interpreter and WASM boundaries, but paused development due to the need for smaller object files and better backends.

**Key points**

- Ghislain proposes a Roc implementation of the WebAssembly Component Model.
- Luke has a work-in-progress "basic-dom" platform used for testing the interpreter and validating the platform host boundary.
- Development on basic-dom stalled because current object files are too large; it requires dev or LLVM backends to be usable.
- Luke intends to share the platform in a minimal working state in the future for others to explore optimizations like skipping JS glue.

**Open questions**

- None explicitly stated.

**Action items**

- Luke plans to revisit and share the basic-dom platform once it reaches a minimal working state.

### command line parsing

- **Channel:** beginners
- **Conversation:** command line parsing
- **Messages:** 1
- **People:** 1
- **Time:** 2:10 AM–2:10 AM (America/Los_Angeles)
- **Participants:** Anton
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/command.20line.20parsing/near/576222688>

**Key links**

- <https://github.com/roc-lang/examples/blob/main/examples/CommandLineArgs/main.roc>
- <https://github.com/roc-lang/roc/releases/tag/alpha4-rolling>

**Summary**

Anton explains that the examples repository uses exact versions and the `alpha4` release, and mentions a future plan to embed the Roc version directly in `.roc` files to prevent incompatibility issues.

**Key points**

- The examples repository specifies exact versions, such as in the `CommandLineArgs` example.
- All examples in the repository currently use Roc `alpha4-rolling`.
- There is a plan to allow specifying the Roc version within the `.roc` file itself.

**Open questions**

- None.

**Action items**

- None.

### Unhelpful err msg for return in expression position

- **Channel:** bugs
- **Conversation:** Unhelpful err msg for return in expression position
- **Messages:** 1
- **People:** 1
- **Time:** 1:56 PM–1:56 PM (America/Los_Angeles)
- **Participants:** Norbert Hajagos
- **Link:** <https://roc.zulipchat.com/#narrow/channel/463736-bugs/topic/Unhelpful.20err.20msg.20for.20return.20in.20expression.20position/near/576355897>

**Key links**

- <https://roc-lang.github.io/roc-playground/#content=bWFpbiEgPSB8X2FyZ3N8IHsKCU9rKHt9KQp9CgpyZXBybyA9IHx8IHsKCSMgYHJldHVybmAgYXQgZXhwcmVzc2lvbiBwb3NpdGlvbgoJbXNnID0gcmV0dXJuIHt9CgkjIHRoZSBmaXg6CgkjIG1zZyA9IHsKCSMgCXJldHVybiB7fQoJIyB9Cgltc2cKfQoKc2ltcGxpZmllZF9yZWFsX3VzZV9jYXNlID0gfGlucHV0fCB7Cgltc2cgPSBtYXRjaCBpbnB1dCB7CgkJImhpIiA9PiAiaGkiCgkJXyA9PiByZXR1cm4gInRoZXJlIgoJCSMgdGhlIGZpeDoKCQkjIF8gPT4gewoJCSMgCXJldHVybiAidGhlcmUiCgkJIyB9Cgl9Cgltc2cKfQoKZXhwZWN0IHJlcHJvKCkgPT0ge30KZXhwZWN0IHNpbXBsaWZpZWRfcmVhbF91c2VfY2FzZSgiaGkiKSA9PSAiaGki>

**Summary**

Norbert Hajagos reports an unhelpful error message in issue #9218 when `return` is used in expression position (e.g., assigned to a variable or inside a match branch) rather than in statement position.

**Key points**

- The user encountered the confusing error while updating the `TryOperatorDesugaring` example.
- The error occurs when `return` is used as an expression (e.g., `msg = return {}`) instead of a statement.
- The fix requires wrapping the `return` in a block (e.g., `msg = { return {} }`).
- The current error message is difficult to decipher without prior knowledge of the restriction.

**Open questions**

- How can the error message be improved to clearly explain that `return` is only allowed in statement position?

**Action items**

- Improve the error message for `return` used in expression position.

### eval snapshots snippet expect

- **Channel:** compiler development
- **Conversation:** eval snapshots snippet expect
- **Messages:** 1
- **People:** 1
- **Time:** 8:30 AM–8:30 AM (America/Los_Angeles)
- **Participants:** Anton
- **Link:** <https://roc.zulipchat.com/#narrow/channel/395097-compiler-development/topic/eval.20snapshots.20snippet.20expect/near/576302428>

**Summary**

Anton provided a brief status update regarding pull request #9215, noting its dependency on other merges.

**Key points**

- PR #9215 is currently open.
- The PR cannot be merged immediately because other PRs need to be merged first.

**Open questions**

- None identified from the transcript.

**Action items**

- None identified from the transcript.

### Roc Examples - migrate to "Headerless" Applications

- **Channel:** ideas
- **Conversation:** Roc Examples - migrate to "Headerless" Applications
- **Messages:** 1
- **People:** 1
- **Time:** 1:49 AM–1:49 AM (America/Los_Angeles)
- **Participants:** Anton
- **Link:** <https://roc.zulipchat.com/#narrow/channel/304641-ideas/topic/Roc.20Examples.20-.20migrate.20to.20"Headerless".20Applications/near/576218377>

**Key links**

- <https://www.roc-lang.org/examples/>

**Summary**

Anton expresses concern regarding a proposal to migrate Roc's official examples to a "Headerless" application format, worrying that this change might prevent users from discovering the standard `basic-cli` platform required for real-world applications.

**Key points**

- A proposal was made to migrate the examples on roc-lang.org from `basic-cli` to a "Headerless" application format.
- Anton worries that users will not transition away from the "tutorial" platform if the examples do not use `basic-cli`.
- The concern is that this could result in users failing to learn how to build real-world Roc programs.

**Open questions**

- None identified in the provided transcript.

**Action items**

- None identified in the provided transcript.
