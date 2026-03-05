---
published: true
date: 2026-03-04
title: Zulip Daily Summary (2026-03-04)
layout: post
categories: [zulip, summary]
---
# Roc Zulip Daily Summary — 2026-03-04

- **Realm:** https://roc.zulipchat.com
- **Window:** 2026-03-04 12:00 AM to 2026-03-05 12:00 AM (America/Los_Angeles)
- **Messages:** 31
- **LLM:** vertex_open_model model=zai-org/glm-5-maas topics=4 ok=4/4

## Top threads

---

### Unexpected type mismatch with parameterised function

**Summary**

Jonathan reported an unexpected type mismatch error when testing a parameterized function involving a recursive `RBTree` type, which also triggered compiler panics and internal errors. Anton identified the root causes as bugs related to handling recursive types and method calls, subsequently opening three pull requests to fix the issues.

**Key points**

- Jonathan encountered a type mismatch error that appeared inconsistently depending on whether the code was in a separate file or run via `roc test`.
- The provided `RBTree.roc` gist caused a `thread ... panic: reached unreachable code` during canonicalization when built from source.
- Jonathan found that the panic was triggered by specific lambda captures in `apply` calls (e.g., `|x| before` vs `|x| x`).
- Anton linked the uninformative type errors (e.g., expecting `X` but got `Error`) to the compiler serializing recursive self-references as errors to break cycles.

**Open questions**

- None explicitly pending; the immediate compiler bugs are being addressed by the PRs.

**Action items**

- Anton is addressing the remaining errors following the merge of the initial fixes.

- **Channel:** beginners
- **Conversation:** Unexpected type mismatch with parameterised function
- **Messages:** 21
- **People:** 2
- **Time:** 3:33 AM–11:29 AM (America/Los_Angeles)
- **Participants:** Jonathan, Anton
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Unexpected.20type.20mismatch.20with.20parameterised.20function/near/577338664>

**Key links**

- [link 1][t1-l1]
- [link 2][t1-l2]

[t1-l1]: https://gist.github.com/jrrrp/ae6fe1e91a1932593e13f790451a8471
[t1-l2]: https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Unexpected.20type.20mismatch.20with.20parameterised.20function/near/577200636

---

### How would FFI python → roc work?

**Summary**

Lukas Juhrich asked how to compile Roc code into a shared library (`.so`) for use with Python FFI, questioning if he needed to write a custom platform to do so. Luke Boswell explained that while `roc build` defaults to executables, platform authors can configure it to output dynamic libraries, pointing to existing WASM and Zig templates as the best available examples.

**Key points**

- A platform module header determines the build target, which can be configured to produce a dynamic library (like `.so`) instead of an executable.
- The `roc glue` tool is intended to assist in generating type-safe interfaces between the platform host (e.g., Python) and Roc.
- The workflow for creating custom platforms and FFI bindings is currently undocumented and considered an advanced topic.
- The `roc-platform-template-zig` repository and WASM platforms serve as the best current references for how to structure platforms.

**Open questions**

- None.

**Action items**

- Look at the WASM platform and the `roc-platform-template-zig` repository for implementation examples.

- **Channel:** beginners
- **Conversation:** How would FFI python → roc work?
- **Messages:** 8
- **People:** 2
- **Time:** 2:10 PM–3:09 PM (America/Los_Angeles)
- **Participants:** Luke Boswell, Lukas Juhrich
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/How.20would.20FFI.20python.20.E2.86.92.20roc.20work.3F/near/577374233>

**Key links**

- [link 1][t2-l1]

[t2-l1]: https://github.com/lukewilliamboswell/roc-platform-template-zig

---

### List concatMany and insert

**Summary**

Based on the provided transcript, the thread appears to be a single message without any replies. Brendan Hansknecht suggests that HAMT (Hash Array Mapped Trie) data structures could be implemented in Roc userspace if a specific need arises.

**Key points**

- HAMT data structures are a potential candidate for user-level implementation in Roc.
- The necessity of such an implementation depends on specific user needs.

**Open questions**

- None identified from the single message.

**Action items**

- None identified from the single message.

- **Channel:** beginners
- **Conversation:** List concatMany and insert
- **Messages:** 1
- **People:** 1
- **Time:** 6:03 PM–6:03 PM (America/Los_Angeles)
- **Participants:** Brendan Hansknecht
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/List.20concatMany.20and.20insert/near/577396783>

---

### compile time evaluation

**Summary**

Brendan Hansknecht agrees with a prior statement regarding the complexity of re-doing type-checking and polymorphism at runtime, suggesting that a simpler approach would involve waiting until after monomorphization to start the interpreter.

**Key points**

- Re-doing type-checking and polymorphism operations at runtime is seen as a complexity driver.
- Kicking off the interpreter after the "mono" (monomorphization) stage is proposed as a simpler alternative.

**Open questions**

- None.

**Action items**

- None.

- **Channel:** compiler development
- **Conversation:** compile time evaluation
- **Messages:** 1
- **People:** 1
- **Time:** 6:05 PM–6:05 PM (America/Los_Angeles)
- **Participants:** Brendan Hansknecht
- **Link:** <https://roc.zulipchat.com/#narrow/channel/395097-compiler-development/topic/compile.20time.20evaluation/near/577396965>
