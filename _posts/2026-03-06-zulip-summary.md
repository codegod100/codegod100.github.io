---
published: true
date: 2026-03-06
title: Zulip Daily Summary (2026-03-06)
layout: post
categories: [zulip, summary]
---
# Roc Zulip Daily Summary — 2026-03-06

- **Realm:** https://roc.zulipchat.com
- **Window:** 2026-03-06 12:00 AM to 2026-03-07 12:00 AM (America/Los_Angeles)
- **Messages:** 24
- **LLM:** vertex_open_model model=zai-org/glm-5-maas topics=4 ok=4/4

## Top threads

---

### Unexpected type mismatch with parameterised function

**Summary**

Jonathan reported a type mismatch error when testing a parameterized `reverse` function inside its own module, a issue that did not occur when testing from an external module. Anton diagnosed an integer overflow panic related to the issue and subsequently provided two PRs to fix the problems.

**Key points**

- Jonathan identified a type mismatch (`I32 != a`) occurring specifically when a generic `reverse` function was tested within the same file using `expect`.
- The error was sensitive to the function's implementation content, not just its signature, as similar generic functions like `noopList` worked fine.
- Anton reproduced the issue, which also triggered a `panic: integer overflow` during testing.
- Steve Howell inquired about the error terminology, noting that "integer overflow" in Zig can refer to an underflow condition.

**Open questions**

- None.

**Action items**

- Review/merge PR #9241 (fixes the integer overflow panic).
- Review/merge PR #9243 (fixes the type mismatch compile error).

- **Channel:** beginners
- **Conversation:** Unexpected type mismatch with parameterised function
- **Messages:** 15
- **People:** 3
- **Time:** 1:41 AM–10:40 AM (America/Los_Angeles)
- **Participants:** Anton, Jonathan, Steve Howell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Unexpected.20type.20mismatch.20with.20parameterised.20function/near/577814445>

**Key links**

- [link 1][t1-l1]

[t1-l1]: https://github.com/roc-lang/roc/blob/main/test/echo/hello.roc

---

### Error handling / new compiler

**Summary**

Jay asked if it is a good time to create a tutorial on Roc's error handling or if they should wait for the new compiler release. Luke Boswell advised that because the release is likely months away, creating content now is acceptable but should include a disclaimer that the rewrite is incomplete and not yet beginner-friendly.

**Key points**

- Jay is interested in creating content specifically about the ergonomics of Roc's error handling.
- The release of the new compiler is estimated to be months away.
- The current state of the rewrite involves partially implemented features and is not considered beginner-friendly.
- Development backends are expected to land soon, after which the team plans to focus on polishing, platforms, and documentation.

**Open questions**

- It is unclear what the plan is regarding updating the website and switching everything across to the new compiler.

**Action items**

- Jay should warn viewers that the compiler rewrite is incomplete if they create a video now.
- Luke Boswell plans to migrate platforms using upgrades recently landed in `roc glue` over the coming week.

- **Channel:** beginners
- **Conversation:** Error handling / new compiler
- **Messages:** 4
- **People:** 2
- **Time:** 11:39 AM–2:03 PM (America/Los_Angeles)
- **Participants:** Luke Boswell, Jay
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Error.20handling.20.2F.20new.20compiler/near/577844937>

---

### Possible debug-68797921 issue on basic-cli

**Summary**

Iain Schmitt encountered an `InvalidHash` error when using a specific nightly Roc compiler build (`debug-68797921`) with `basic-cli` 0.20.0, but the code worked correctly with the `alpha4` release.

**Key points**

- The user was following the tutorial using a nightly compiler build identified as `debug-68797921`.
- The error occurred because the nightly compiler uses a different hash check mechanism compared to the alpha release required for `basic-cli` 0.20.0.
- Anton clarified that `basic-cli` 0.20.0 requires Roc alpha4, while the newest nightly builds require building the platform from source.
- Anton created an issue (#9242) to improve the error message for this version mismatch scenario.

**Open questions**

- None.

**Action items**

- None.

- **Channel:** beginners
- **Conversation:** Possible debug-68797921 issue on basic-cli
- **Messages:** 4
- **People:** 2
- **Time:** 8:55 AM–9:02 AM (America/Los_Angeles)
- **Participants:** Anton, Iain Schmitt
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Possible.20debug-68797921.20issue.20on.20basic-cli/near/577796339>

**Key links**

- [link 1][t3-l1]
- [link 2][t3-l2]
- [link 3][t3-l3]
- [link 4][t3-l4]

[t3-l1]: https://github.com/roc-lang/basic-cli/releases/download/0.20.0/X73hGh05nNTkDHU06FHC0YfFaQB1pimX7gncRcao5mU.tar.br
[t3-l2]: https://github.com/roc-lang/nightlies/releases/tag/nightly-2026-March-06-a02d228
[t3-l3]: https://github.com/roc-lang/basic-cli/pull/423
[t3-l4]: https://github.com/roc-lang/roc/blob/main/docs/mini-tutorial-new-compiler.md

---

### Occasional panic associated with list append

**Summary**

Jonathan reported an intermittent panic occurring when comparing lists of tags, specifically triggered by using a custom `keep_oks` function with `list_append`, while similar code using numbers works fine.

**Key points**

- The panic happens 90% of the time when comparing a list containing a tag (`Res`) but succeeds 100% of the time when comparing a list of numbers (`1`).
- The failure is believed to be an assertion failure within `asRocList`, called during the low-level builtin for `list_append`.
- The issue persists regardless of whether the code is written using a `for` loop or `fold` style.
- The bug occurs when running with `roc --no-cache`.

**Open questions**

- What is the root cause of the assertion failure in `asRocList`?
- Why does the panic occur intermittently (90% of the time) rather than consistently?
- Why does the type of element (tag vs. number) affect the outcome?

**Action items**

- Investigate the `asRocList` assertion failure during `list_append`.
- Debug the issue further once symbols are available (currently stripped).

- **Channel:** bugs
- **Conversation:** Occasional panic associated with list append
- **Messages:** 1
- **People:** 1
- **Time:** 11:54 AM–11:54 AM (America/Los_Angeles)
- **Participants:** Jonathan
- **Link:** <https://roc.zulipchat.com/#narrow/channel/463736-bugs/topic/Occasional.20panic.20associated.20with.20list.20append/near/577826612>
