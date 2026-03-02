---
published: true
date: 2026-03-01
title: Zulip Daily Summary (2026-03-01)
layout: post
categories: [zulip, summary]
---
# Roc Zulip Daily Summary — 2026-03-01

- **Realm:** https://roc.zulipchat.com
- **Window:** 2026-03-01 12:00 AM to 2026-03-02 12:00 AM (America/Los_Angeles)
- **Messages:** 5
- **LLM:** vertex_open_model model=zai-org/glm-5-maas topics=2 ok=2/2

## Top threads

---

### List concatMany and insert

**Summary**

Jonathan inquires about the existence of a `List` `insert` function or a `concatMany` function to optimize memory allocation, and Luke points him to legacy documentation for the `join` function while suggesting `Dict` for insert-heavy use cases.

**Key points**

- Jonathan is looking for a way to insert into a `List` without allocating multiple intermediate arrays.
- Luke suggests that the old documentation (specifically `join`) is being ported to the new compiler without major changes.
- Luke recommends `Dict` for data structures that require insert-friendly operations, though he notes it may not be fully implemented yet.
- Jonathan mentions he is attempting to implement a Hash Array Mapped Trie (HAMT) in Roc as a learning exercise.

**Open questions**

- Are tree-based data structures (like Scala Vector or Clojure PersistentVector) planned for Roc?

**Action items**

- Jonathan plans to try implementing `join` and other list functions in pure Roc.

- **Channel:** beginners
- **Conversation:** List concatMany and insert
- **Messages:** 3
- **People:** 2
- **Time:** 11:00 AM–11:50 AM (America/Los_Angeles)
- **Participants:** Jonathan, Luke Boswell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/List.20concatMany.20and.20insert/near/576548521>

**Key links**

- [link 1][t1-l1]
- [link 2][t1-l2]

[t1-l1]: https://www.roc-lang.org/builtins/alpha4/List/
[t1-l2]: https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/List.20concatMany.20and.20insert/near/576547900

---

### Value showing up as opaque type

**Summary**

Jonathan encountered a compiler bug where a value appeared as an opaque type and caused a segfault when accessing the second payload of a multi-payload tag, which was resolved by refactoring the tag to use a record payload instead.

**Key points**

- The issue occurred when pattern matching on a tag with multiple payloads, specifically `Just(U64, Str)`.
- Printing the matched value `v` resulted in an opaque type output, and subsequent operations like equality checks caused a crash (status 139).
- The compiler version used was a debug build (a3741118) on macOS Apple Silicon.
- The bug was bypassed by changing the tag definition to use a record payload: `Just({index: U64, value: v})`.

**Open questions**

- What is the root cause of the failure to handle multiple payloads in tag types correctly?

**Action items**

- Investigate the handling of multi-payload tags in the compiler to prevent the segfault and type display error.

- **Channel:** beginners
- **Conversation:** Value showing up as opaque type
- **Messages:** 2
- **People:** 1
- **Time:** 12:51 PM–1:14 PM (America/Los_Angeles)
- **Participants:** Jonathan
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Value.20showing.20up.20as.20opaque.20type/near/576554291>
