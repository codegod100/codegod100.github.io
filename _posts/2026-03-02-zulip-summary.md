---
published: true
date: 2026-03-02
title: Zulip Daily Summary (2026-03-02)
layout: post
categories: [zulip, summary]
---
# Roc Zulip Daily Summary — 2026-03-02

- **Realm:** https://roc.zulipchat.com
- **Window:** 2026-03-02 12:00 AM to 2026-03-03 12:00 AM (America/Los_Angeles)
- **Messages:** 14
- **LLM:** vertex_open_model model=zai-org/glm-5-maas topics=5 ok=5/5

## Top threads

---

### math functions in new compiler

**Summary**

Guillaume Sarisson asked how to use math functions in the new compiler and whether the `Num` module still exists. Luke Boswell explained that the module is gone, directed them to the `Builtin.roc` file, and provided examples of the current syntax for arithmetic operations.

**Key points**

- The `Num` module no longer exists in the new compiler.
- Built-in functions are now defined in `src/build/roc/Builtin.roc`.
- Math operations can be performed using type-specific functions (e.g., `U16.plus`, `U32.div_by`) or standard infix operators.
- The syntax supports a "follower" style where the first argument precedes the function call (e.g., `12.U64.plus(12)`).

**Open questions**

- None.

**Action items**

- None.

- **Channel:** beginners
- **Conversation:** math functions in new compiler
- **Messages:** 6
- **People:** 2
- **Time:** 11:16 PM–11:25 PM (America/Los_Angeles)
- **Participants:** Luke Boswell, Guillaume Sarisson
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/math.20functions.20in.20new.20compiler/near/576902958>

**Key links**

- [link 1][t1-l1]

[t1-l1]: https://github.com/roc-lang/roc/blob/3fa8df31997e3e233d5bda63eec8737ccd3ce941/src/build/roc/Builtin.roc#L4

---

### List concatMany and insert

**Summary**

Anton grants permission to add `List.join` and `List.insert` to the `Builtin.roc` file, noting that a Roc implementation is acceptable for now with the possibility of a low-level optimization later.

**Key points**

- `List.join` and `List.insert` may be added to `Builtin.roc`.
- It is acceptable to implement `List.join` in Roc, even if a low-level version might be added later.
- LLVM optimization may make the underlying implementation details (like tree-based arrays) irrelevant for release builds, though it could still matter for dev backends.

**Open questions**

- None.

**Action items**

- Add `List.join` to `Builtin.roc`.
- Add `List.insert` to `Builtin.roc`.

- **Channel:** beginners
- **Conversation:** List concatMany and insert
- **Messages:** 3
- **People:** 1
- **Time:** 8:15 AM–8:25 AM (America/Los_Angeles)
- **Participants:** Anton
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/List.20concatMany.20and.20insert/near/576742147>

**Key links**

- [link 1][t2-l1]

[t2-l1]: https://github.com/roc-lang/roc/blob/main/src/build/roc/Builtin.roc

---

### Reassign or redeclare a constant?

**Summary**

Hubert Małkowski inquired about the rationale for avoiding variable shadowing in Roc, and Anton explained that the restriction is intended to prevent bugs and confusion while simplifying the language.

**Key points**

- A user asked why Roc avoids shadowing.
- The reasons given were to avoid bugs, prevent confusion, and simplify the language design.

**Open questions**

- None.

**Action items**

- None.

- **Channel:** beginners
- **Conversation:** Reassign or redeclare a constant?
- **Messages:** 2
- **People:** 2
- **Time:** 7:50 AM–8:03 AM (America/Los_Angeles)
- **Participants:** Anton, Hubert Małkowski
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Reassign.20or.20redeclare.20a.20constant.3F/near/576737199>

---

### Datastar

**Summary**

Richard Feldman shared a video interview about Datastar, describing it as a project that aligns with the htmx philosophy but prioritizes performance-obsessed implementation.

**Key points**

- Datastar is described as having an "htmx philosophy" while being "performance-obsessed" in its implementation.
- The project boasts a small footprint of 10kb total and requires no npm.
- Feldman expressed strong enthusiasm for the interview and the project's pitch.

**Open questions**

- None.

**Action items**

- None.

- **Channel:** off topic
- **Conversation:** Datastar
- **Messages:** 2
- **People:** 1
- **Time:** 4:13 PM–4:13 PM (America/Los_Angeles)
- **Participants:** Richard Feldman
- **Link:** <https://roc.zulipchat.com/#narrow/channel/306878-off-topic/topic/Datastar/near/576852801>

**Key links**

- [link 1][t4-l1]
- [link 2][t4-l2]

[t4-l1]: https://youtu.be/tU9vSXUKGHw?si=goM55YN5PyIMXS2H&t=1633
[t4-l2]: https://data-star.dev/

---

### Value showing up as opaque type

**Summary**

Anton reports encountering a "panic: reached unreachable code" error and has created issue #9229 to track it.

**Key points**

- The error message observed was "panic: reached unreachable code".
- A specific issue, #9229, was created to document the problem.

**Open questions**

- None.

**Action items**

- None.

- **Channel:** beginners
- **Conversation:** Value showing up as opaque type
- **Messages:** 1
- **People:** 1
- **Time:** 9:07 AM–9:07 AM (America/Los_Angeles)
- **Participants:** Anton
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Value.20showing.20up.20as.20opaque.20type/near/576780497>
