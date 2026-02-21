---
published: true
date: 2026-02-20
title: Zulip Daily Summary (2026-02-20)
layout: post
categories: [zulip, summary]
---
# Roc Zulip Daily Summary — 2026-02-20

- **Realm:** https://roc.zulipchat.com
- **Window:** 2026-02-20 12:00 AM to 2026-02-21 12:00 AM (America/Los_Angeles)
- **Messages:** 9
- **LLM:** vertex_open_model model=zai-org/glm-5-maas topics=3 ok=3/3

## Top threads

### Roc crashed: Builtin.U8 does not implement len()

- **Channel:** bugs
- **Conversation:** Roc crashed: Builtin.U8 does not implement len()
- **Messages:** 7
- **People:** 3
- **Time:** 12:41 AM–11:33 AM (America/Los_Angeles)
- **Participants:** Lukas Juhrich, Anton, Luke Boswell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/463736-bugs/topic/Roc.20crashed.3A.20Builtin.2EU8.20does.20not.20implement.20len.28.29/near/575015482>

**Key links**

- <https://github.com/lukewilliamboswell/roc-platform-template-zig/releases/download/0.6/2BfGn4M9uWJNhDVeMghGeXNVDFijMfPsmmVeo6M4QjKX.tar.zst>
- <https://roc.zulipchat.com/#narrow/channel/463736-bugs/topic/Roc.20crashed.3A.20Builtin.2EU8.20does.20not.20implement.20len.28.29/near/574897752>
- <https://roc.zulipchat.com/#narrow/channel/463736-bugs/topic/Roc.20crashed.3A.20Builtin.2EU8.20does.20not.20implement.20len.28.29/near/574929177>

**Summary**

Lukas Juhrich reported a Roc compiler crash with the error "Builtin.U8 does not implement len()" and asked for guidance on how to debug the issue themselves to learn about the compiler, rather than just obtaining a fix.

**Key points**

- The crash occurs in a snippet involving `Str.to_utf8`, pattern matching on `bytes.first()`, and a custom `take_while` function.
- Anton suggested using AI to fix the bug and running `zig build minici` for testing, noting that difficult bugs require deep expertise or help from domain experts.
- Luke Boswell identified that since `roc check` passes, the bug is likely in the interpreter, not the type checker.
- Luke recommended creating a snapshot test (`zig build snapshot -- path/to/snapshot.md`) to narrow down the issue and using `zig build roc` for faster rebuilds.

**Open questions**

- What is the root cause of the "Builtin.U8 does not implement len()" crash?

**Action items**

- Create a snapshot test to reproduce the bug and generate human-readable IRs.
- If the snapshot test doesn't reproduce it, use the `trace-eval` flag or print debugging to investigate the interpreter.

### .. vs _

- **Channel:** compiler development
- **Conversation:** .. vs _
- **Messages:** 1
- **People:** 1
- **Time:** 1:58 AM–1:58 AM (America/Los_Angeles)
- **Participants:** Anton
- **Link:** <https://roc.zulipchat.com/#narrow/channel/395097-compiler-development/topic/.2E.2E.20vs.20_/near/574903223>

**Summary**

Anton expressed gratitude and appreciation towards Jared Ramirez.

**Key points**

- Anton thanked Jared Ramirez for a previous contribution or clarification.
- The reaction was positive, indicated by the heart emoji.

**Open questions**

- None

**Action items**

- None

### Worklog (Draft PRs and coordination)

- **Channel:** contributing
- **Conversation:** Worklog (Draft PRs and coordination)
- **Messages:** 1
- **People:** 1
- **Time:** 4:17 AM–4:17 AM (America/Los_Angeles)
- **Participants:** Anton
- **Link:** <https://roc.zulipchat.com/#narrow/channel/316715-contributing/topic/Worklog.20.28Draft.20PRs.20and.20coordination.29/near/574927485>

**Key links**

- <https://roc.zulipchat.com/#narrow/channel/316715-contributing/topic/Worklog.20.28Draft.20PRs.20and.20coordination.29/near/574506552>

**Summary**

Anton announced that the Pull Request for implementing file imports is ready for review.

**Key points**

- The feature being implemented is file imports, using the syntax `import "README.md" as readme : Str`.
- The relevant Pull Request is numbered #9187.

**Open questions**

- None

**Action items**

- Review PR#9187.
