---
published: true
date: 2026-03-08
title: Zulip Daily Summary (2026-03-08)
layout: post
categories: [zulip, summary]
---
# Roc Zulip Daily Summary — 2026-03-08

- **Realm:** https://roc.zulipchat.com
- **Window:** 2026-03-08 12:00 AM to 2026-03-09 12:00 AM (America/Los_Angeles)
- **Messages:** 10
- **LLM:** vertex_open_model model=zai-org/glm-5-maas topics=2 ok=2/2

## Top threads

---

### subscript operator

**Summary**

Norbert Hajagos inquired about the desired behavior for `List.replace` and `List.set` when given an out-of-bounds index, referencing a suggestion that they should crash to prioritize correctness. Richard Feldman decided that these functions should return `Try` types rather than crashing or panicking, allowing the team to evaluate the ergonomics of this approach in practice.

**Key points**

- Norbert Hajagos is planning a PR to make `List.subscript` an alias to `List.get` and is currently implementing `List.replace` and `List.set`.
- Research indicated that most languages treat out-of-bounds access as a contract violation, often resulting in a crash or exception.
- Richard Feldman ruled out runtime panics for this scenario, noting that crashes in the standard library are generally reserved for integer overflow, out-of-memory, and division by zero.
- The decision was made to implement `List.replace` and `List.set` as `Try` types to see how the design performs in practice.

**Open questions**

- None.

**Action items**

- Norbert Hajagos to implement `List.replace` and `List.set` using the `Try` return type.

- **Channel:** ideas
- **Conversation:** subscript operator
- **Messages:** 9
- **People:** 2
- **Time:** 10:41 AM–1:58 PM (America/Los_Angeles)
- **Participants:** Richard Feldman, Norbert Hajagos
- **Link:** <https://roc.zulipchat.com/#narrow/channel/304641-ideas/topic/subscript.20operator/near/578037288>

**Key links**

- [link 1][t1-l1]
- [link 2][t1-l2]
- [link 3][t1-l3]
- [link 4][t1-l4]
- [link 5][t1-l5]

[t1-l1]: https://roc.zulipchat.com/#narrow/channel/304641-ideas/topic/subscript.20operator/near/540323565
[t1-l2]: https://roc.zulipchat.com/#narrow/channel/304641-ideas/topic/subscript.20operator/near/540460871
[t1-l3]: https://effect-ts.github.io/effect/effect/Array.ts.html#insertat
[t1-l4]: https://docs.inko-lang.org/std/main/module/std/array/Array/#method.remove_at
[t1-l5]: https://hexdocs.pm/elixir/1.12/List.html#replace_at/3

---

### Roc Online Meetup Mar 2026

**Summary**

Luke Boswell announced the Roc Online Meetup scheduled for March 2026, providing the meeting link and a repository for previous recordings while inviting attendees to propose presentations.

**Key points**

- The meeting is to be held via Google Meet.
- Participants are encouraged to comment with presentation ideas.
- Videos of previous meetups are accessible via a provided Google Drive link.

**Open questions**

- None

**Action items**

- None

- **Channel:** gatherings
- **Conversation:** Roc Online Meetup Mar 2026
- **Messages:** 1
- **People:** 1
- **Time:** 9:51 PM–9:51 PM (America/Los_Angeles)
- **Participants:** Luke Boswell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/303057-gatherings/topic/Roc.20Online.20Meetup.20Mar.202026/near/578072058>

**Key links**

- [link 1][t2-l1]
- [link 2][t2-l2]

[t2-l1]: https://meet.google.com/dcb-eaxn-zxt
[t2-l2]: https://drive.google.com/drive/folders/1OrgVPE6qGx34MT8oP2aNsop1oAs3_EVl?usp=share_link
