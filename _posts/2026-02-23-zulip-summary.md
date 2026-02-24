---
published: true
date: 2026-02-23
title: Zulip Daily Summary (2026-02-23)
layout: post
categories: [zulip, summary]
---
# Roc Zulip Daily Summary — 2026-02-23

- **Realm:** https://roc.zulipchat.com
- **Window:** 2026-02-23 12:00 AM to 2026-02-24 12:00 AM (America/Los_Angeles)
- **Messages:** 23
- **LLM:** vertex_open_model model=zai-org/glm-5-maas topics=4 ok=4/4

## Top threads

### stop one function from being exposed

- **Channel:** beginners
- **Conversation:** stop one function from being exposed
- **Messages:** 11
- **People:** 3
- **Time:** 6:34 AM–7:39 AM (America/Los_Angeles)
- **Participants:** Richard Feldman, Anton, Fabian Schmalzried
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/stop.20one.20function.20from.20being.20exposed/near/575327921>

**Key links**

- <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/stop.20one.20function.20from.20being.20exposed/near/575315715>

**Summary**

The thread clarifies that in Roc, functions are only exposed if they are associated with the module's type, meaning normal top-level functions and type aliases are private by default.

**Key points**

- Normal top-level functions are private to the module and not exposed to importers.
- Only functions associated with the module's type are exposed when the module is imported.
- Top-level type aliases with names different from the filename are also private to the module.
- The design replaces the concept of manually exposing or hiding items with a model where importing a module grants access only to its associated type and its items.

**Open questions**

- None.

**Action items**

- None.

### parse error with -> and lambda

- **Channel:** compiler development
- **Conversation:** parse error with -> and lambda
- **Messages:** 6
- **People:** 3
- **Time:** 6:28 AM–6:23 PM (America/Los_Angeles)
- **Participants:** Anton, Luke Boswell, Richard Feldman
- **Link:** <https://roc.zulipchat.com/#narrow/channel/395097-compiler-development/topic/parse.20error.20with.20-.3E.20and.20lambda/near/575438500>

**Key links**

- <https://github.com/roc-lang/roc/pull/9197>

**Summary**

Anton reported a parse error when piping into a lambda using the `->` operator, and Richard Feldman confirmed it should be supported but likely was never implemented. Luke Boswell subsequently implemented a fix for the issue.

**Key points**

- Piping into a lambda with `->` causes a parse error (`expr_arrow_expects_ident`).
- This functionality was intended but missing from the compiler.
- A GitHub issue (#9195) was created to track the bug.
- The issue was fixed in PR #9197.

**Open questions**

- None.

**Action items**

- None.

### Crash in recursive code

- **Channel:** beginners
- **Conversation:** Crash in recursive code
- **Messages:** 3
- **People:** 2
- **Time:** 10:46 AM–11:04 AM (America/Los_Angeles)
- **Participants:** Claude Précourt, Anton
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Crash.20in.20recursive.20code/near/575377508>

**Key links**

- <https://github.com/roc-lang/basic-cli/releases/download/alpha-0/HVZonS7HStbvGwhqvDZE1HreyDfqD6tayzFbi9rAUXYN.tar.zst>

**Summary**

Claude Précourt reported a crash in a recursive Roc application designed to walk directories, noting that the recursion fails to go deeper than 7 levels and consistently crashes with a specific memory error on certain root paths.

**Key points**

- The application walks directories starting from a command line argument using the latest `basic-cli` platform and Roc nightly build.
- The crash produces the error: `Roc crashed: RocList.refcount: getAllocationDataPtr returned null`.
- The recursion depth is limited to 7 levels, and the crash is consistent for specific directories but does not occur for all root paths.

**Open questions**

- What is the root cause of the `RocList.refcount` crash and the recursion depth limit?

**Action items**

- Anton to investigate the issue and provide an AI prompt to assist with debugging the following day.

### Roc Online Meetup Feb 2026

- **Channel:** gatherings
- **Conversation:** Roc Online Meetup Feb 2026
- **Messages:** 3
- **People:** 2
- **Time:** 2:15 AM–6:52 AM (America/Los_Angeles)
- **Participants:** Steve Howell, Dan G Knutson
- **Link:** <https://roc.zulipchat.com/#narrow/channel/303057-gatherings/topic/Roc.20Online.20Meetup.20Feb.202026/near/575316197>

**Key links**

- <https://devblogs.microsoft.com/dotnet/introducing-c-source-generators/>

**Summary**

Steve Howell shared positive feedback regarding a video on compiler architecture, specifically noting how it clarified lower-level compilation concepts and Zig's optimization strategies. Dan G Knutson followed up on a previous discussion by sharing a link about C# Source Generators and proposing a similar feature for Roc to handle shader bindings.

**Key points**

- Steve Howell reported a significant increase in his understanding of compiler architecture after watching the first 25 minutes of a video.
- The video explained how the new Zig compiler avoids heap allocation for lambda sets and uses unions to minimize binary size for polymorphic functions.
- Dan G Knutson referenced a C# feature, Source Generators, which is used in 2D games for strongly-typed access to animation frames.
- Dan G Knutson is considering implementing a similar approach using templates in Roc to create strongly typed shader bindings.

**Open questions**

- None.

**Action items**

- None.
