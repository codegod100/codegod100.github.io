---
published: true
date: 2026-02-17
title: Zulip Daily Summary (2026-02-17)
layout: post
categories: [zulip, summary]
---
# Roc Zulip Daily Summary — 2026-02-17

- **Realm:** https://roc.zulipchat.com
- **Window:** 2026-02-17 12:00 AM to 2026-02-18 12:00 AM (America/Los_Angeles)
- **Messages:** 45
- **LLM:** vertex_open_model model=zai-org/glm-5-maas topics=5 ok=5/5

## Top threads

### Associated type restriction

- **Channel:** beginners
- **Conversation:** Associated type restriction
- **Messages:** 20
- **People:** 3
- **Time:** 2:50 PM–5:55 PM (America/Los_Angeles)
- **Participants:** Jonathan, Jared Ramirez, Luke Boswell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Associated.20type.20restriction/near/574416866>

**Key links**

- <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Associated.20type.20restriction/near/574399818>

**Summary**

Jonathan asked how to add type parameter restrictions (like `where` clauses) to type definitions in Roc, specifically for cases like an Association List requiring comparable keys, but found that the compiler prohibits `where` clauses inside type declarations.

**Key points**

- The Roc compiler currently forbids defining `where` clauses inside type declarations.
- Luke suggested a potential syntax for aliasing `where` clauses into interfaces (e.g., `HasEq(a)`), though it was unclear if this is currently valid.
- Jared advised that putting constraints on types is an anti-pattern in Roc; constraints should be placed on individual functions instead.
- Placing constraints on types forces those constraints to propagate to all function signatures involving that type, even functions (like `size`) that do not use the restricted functionality (e.g., hashing).

**Open questions**

- Are there specific scenarios where type-level constraints would be considered beneficial or necessary (e.g., to prevent breaking changes)?
- Does the record builder suffix notation allow bypassing "smart constructor" style type restrictions?

**Action items**

- Jared provided a link to a previous discussion thread for further reading on the topic.

### ✔ Strange parsing error

- **Channel:** beginners
- **Conversation:** ✔ Strange parsing error
- **Messages:** 13
- **People:** 4
- **Time:** 5:09 PM–5:45 PM (America/Los_Angeles)
- **Participants:** Luke Boswell, Joshua Warner, Claude Précourt, Notification Bot
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/.E2.9C.94.20Strange.20parsing.20error/near/574416150>

**Summary**

Claude Précourt encountered a parsing error when using the new Roc compiler, which was quickly resolved by realizing that a lambda function body required a block expression. The discussion then shifted to potential future improvements for the compiler's syntax error reporting, including indentation tracking and machine learning models.

**Key points**

- The user's error was caused by omitting curly braces `{}` around a lambda function body containing multiple expressions.
- Luke Boswell noted that there were previous discussions about improving error detection for this specific syntax mistake.
- Joshua Warner suggested tracking indentation as a hint for the parser to provide better error messages.
- Joshua Warner proposed an R&D idea to train a small language model (approx. 20m parameters) to automatically suggest fixes for syntax errors.

**Open questions**

- Should a GitHub Issue be created to track the research and development of better syntax error reporting?

**Action items**

- Consider creating a GitHub Issue to track the syntax error improvement concepts (indentation tracking or ML models).

### Num.atan gives inconsistent values

- **Channel:** bugs
- **Conversation:** Num.atan gives inconsistent values
- **Messages:** 8
- **People:** 2
- **Time:** 12:18 PM–2:34 PM (America/Los_Angeles)
- **Participants:** Luke Boswell, Guillaume Sarisson
- **Link:** <https://roc.zulipchat.com/#narrow/channel/463736-bugs/topic/Num.2Eatan.20gives.20inconsistent.20values/near/574397995>

**Key links**

- <https://github.com/roc-lang/roc/pull/9186>

**Summary**

Guillaume Sarisson reported that the `Num.atan` function in the Roc nightly compiler returns inconsistent values, specifically returning `0` for fractional inputs but large incorrect numbers for integer inputs, which Luke Boswell subsequently fixed.

**Key points**

- `Num.atan` returns `0` for `1/1` but a large incorrect float for `1`.
- The issue occurred in a Roc nightly build from September 2025.
- Luke Boswell identified the issue and provided a fix in GitHub PR #9186.
- The maintainers are generally prioritizing active users for the older compiler support.

**Open questions**

- None.

**Action items**

- None.

### daily summary

- **Channel:** show and tell
- **Conversation:** daily summary
- **Messages:** 3
- **People:** 2
- **Time:** 2:11 PM–2:53 PM (America/Los_Angeles)
- **Participants:** nandi, Steve Howell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/304902-show-and-tell/topic/daily.20summary/near/574400027>

**Key links**

- <https://roc.zulipchat.com/#narrow/channel/304902-show-and-tell/topic/daily.20summary/near/573742907>
- <https://codegod100.github.io/zulip/summary/2026/02/16/zulip-summary.html>
- <https://roc.zulipchat.com/#narrow/channel/304902-show-and-tell/topic/daily.20summary/near/574031998>

**Summary**

Nandi implemented a suggestion from Rick Hull to host a daily Zulip summary on GitHub Pages instead of Google Docs. Nandi also replied to Steve Howell regarding the Lean Prover, mentioning a personal learning project involving the Riemann Hypothesis.

**Key points**

- Nandi created a hosted HTML summary report at `codegod100.github.io` based on prior feedback.
- Nandi acknowledged the context that the summary covers Zulip activity specifically.
- Nandi expressed being a fan of the Lean Prover and discussed using it to attempt proving the Riemann Hypothesis.

**Open questions**

- None

**Action items**

- None

### .. vs _

- **Channel:** compiler development
- **Conversation:** .. vs _
- **Messages:** 1
- **People:** 1
- **Time:** 3:29 AM–3:29 AM (America/Los_Angeles)
- **Participants:** Anton
- **Link:** <https://roc.zulipchat.com/#narrow/channel/395097-compiler-development/topic/.2E.2E.20vs.20_/near/574269170>

**Key links**

- <https://github.com/roc-lang/basic-cli/releases/download/0.20.0/X73hGh05nNTkDHU06FHC0YfFaQB1pimX7gncRcao5mU.tar.br>

**Summary**

Anton reported a type mismatch error in "new Roc" when using the `?` operator to propagate errors in a function with an open error type annotation (`[Exit(I32), ..]`), contrasting it with "old Roc" where the code structure was valid.

**Key points**

- The error occurs because the error type `EmptyStrErr` from the `line` function does not match the function body's annotated open error type `[Exit(I32), ..]`.
- The compiler error indicates that the `?` operator returns `Try({ }, [EmptyStrErr])` while the function body evaluates to `Try({ }, [Exit(I32), ..])`.
- The code example uses `Try` and an open error set annotation (`..`) which appears to be a feature of the "new Roc" syntax shown.
- A comparison is made to "old Roc" (using `Result` and a `cli` platform), implying the expectation that this code should work or that the behavior has changed.

**Open questions**

- Is the type mismatch a bug in the compiler's handling of open error types (`..`) with the `?` operator, or a user error in the annotation?
- What is the correct syntax or approach in "new Roc" to allow `?` to propagate errors into an open error set?

**Action items**

- Investigate why the compiler fails to unify `[EmptyStrErr]` with `[Exit(I32), ..]` in this context.
