---
published: true
date: 2026-03-09
title: Zulip Daily Summary (2026-03-09)
layout: post
categories: [zulip, summary]
---
# Roc Zulip Daily Summary — 2026-03-09

- **Realm:** https://roc.zulipchat.com
- **Window:** 2026-03-09 12:00 AM to 2026-03-10 12:00 AM (America/Los_Angeles)
- **Messages:** 26
- **LLM:** vertex_open_model model=zai-org/glm-5-maas topics=3 ok=3/3

## Top threads

---

### passing stuff down the stack

**Summary**

Steve Howell expresses frustration with the boilerplate required to pass objects or callbacks down a deep call stack while avoiding global state, prompting a discussion on potential solutions like context objects, record composition, and message-passing architectures.

**Key points**

- Steve Howell identifies passing dependencies through multiple intermediate functions solely to reach a deeply nested handler (like a click event) as a major nuisance.
- Luke Boswell suggests using a `ctx` (context) object and notes that in Roc, composing records allows for flexible type-safe handling of partial contexts.
- Steve Howell critiques generic context objects, noting they can lead to optional fields when higher-level functions cannot fully populate the required data.
- Brendan Hansknecht cites Elm's message/command pattern as a solution that allows subcomponents to generate necessary messages without being dependent on the higher call chain.

**Open questions**

- None specified.

**Action items**

- None specified.

- **Channel:** off topic
- **Conversation:** passing stuff down the stack
- **Messages:** 16
- **People:** 3
- **Time:** 9:14 PM–10:47 PM (America/Los_Angeles)
- **Participants:** Steve Howell, Brendan Hansknecht, Luke Boswell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/306878-off-topic/topic/passing.20stuff.20down.20the.20stack/near/578312025>

---

### Occasional panic associated with List.len

**Summary**

Jonathan encountered crashes when attempting to use the dev backend with a minimal Roc application, initially suspecting caching issues, but learned the backend is currently non-functional.

**Key points**

- Jonathan attempted to build an empty `main.roc` using the dev backend, which resulted in a crash trace involving `MonoExprCodeGen`.
- Luke Boswell clarified that the dev backend on main is currently less than 1% functioning due to a large refactor residing on another branch.
- Jonathan had previously attempted the interpreter backend but switched due to it being deprecated.

**Open questions**

- None.

**Action items**

- None.

- **Channel:** bugs
- **Conversation:** Occasional panic associated with List.len
- **Messages:** 5
- **People:** 2
- **Time:** 4:29 PM–4:34 PM (America/Los_Angeles)
- **Participants:** Jonathan, Luke Boswell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/463736-bugs/topic/Occasional.20panic.20associated.20with.20List.2Elen/near/578273614>

**Key links**

- [link 1][t2-l1]

[t2-l1]: https://github.com/lukewilliamboswell/roc-platform-template-zig/releases/download/0.6/2BfGn4M9uWJNhDVeMghGeXNVDFijMfPsmmVeo6M4QjKX.tar.zst

---

### subscript operator

**Summary**

The thread discusses the requirements for using custom types as `Dict` keys in Roc, confirming that types must be hashable and equatable, and outlines a future design involving static dispatch and `where` clauses to enforce these constraints.

**Key points**

- `Dict` keys in Roc currently require types that implement `Hash` and `Eq`.
- For most types, `Hash` and `Eq` implementations can be automatically derived by the compiler.
- A planned mechanism using static dispatch would allow types to define or infer implementations for functions like `equals` and `hash`.
- `Dict` definitions will eventually use `where` clauses to constrain keys to types possessing the necessary `equals` and `hash` implementations.

**Open questions**

- None.

**Action items**

- None.

- **Channel:** ideas
- **Conversation:** subscript operator
- **Messages:** 5
- **People:** 3
- **Time:** 10:18 PM–11:27 PM (America/Los_Angeles)
- **Participants:** Brendan Hansknecht, Luke Boswell, Kasper Møller Andersen
- **Link:** <https://roc.zulipchat.com/#narrow/channel/304641-ideas/topic/subscript.20operator/near/578315277>
