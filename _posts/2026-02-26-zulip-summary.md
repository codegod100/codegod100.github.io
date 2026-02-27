---
published: true
date: 2026-02-26
title: Zulip Daily Summary (2026-02-26)
layout: post
categories: [zulip, summary]
---
# Roc Zulip Daily Summary — 2026-02-26

- **Realm:** https://roc.zulipchat.com
- **Window:** 2026-02-26 12:00 AM to 2026-02-27 12:00 AM (America/Los_Angeles)
- **Messages:** 40
- **LLM:** vertex_open_model model=zai-org/glm-5-maas topics=6 ok=6/6

## Top threads

### Multiple roc.exe versions

- **Channel:** beginners
- **Conversation:** Multiple roc.exe versions
- **Messages:** 23
- **People:** 2
- **Time:** 12:02 PM–2:01 PM (America/Los_Angeles)
- **Participants:** Luke Boswell, Daren
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Multiple.20roc.2Eexe.20versions/near/576131087>

**Key links**

- <https://github.com/lukewilliamboswell/roc-platform-template-zig/releases/download/0.6/2BfGn4M9uWJNhDVeMghGeXNVDFijMfPsmmVeo6M4QjKX.tar.zst>

**Summary**

Daren encountered a kernel panic when trying to run a nightly Roc executable alongside a locally built version on Windows, which was resolved by clearing the shared Roc cache.

**Key points**

- Running a nightly `roc.exe` caused a panic ("integer does not fit in destination type") when a cache directory from a local build (sharing the same version hash) existed.
- Deleting the cache directory (`C:\Users\...\AppData\Roaming\Roc`) fixed the panic, confirming that different builds with the same version hash were conflicting over the cache.
- The version hash is derived from the git sha; therefore, uncommitted local builds can share a hash with a nightly, causing them to write to the same cache directory.
- Daren praised the smooth process of building the Zig-based compiler from source.

**Open questions**

- The underlying cause of the panic suggests a potential deeper bug regarding the serialization of modules in the cache.

**Action items**

- To run multiple builds concurrently without conflict, ensure they have different version hashes (e.g., by committing changes to generate a new sha).

### Roc Examples - migrate to "Headerless" Applications

- **Channel:** ideas
- **Conversation:** Roc Examples - migrate to "Headerless" Applications
- **Messages:** 7
- **People:** 3
- **Time:** 4:24 AM–11:36 PM (America/Los_Angeles)
- **Participants:** Luke Boswell, Notification Bot, Steve Howell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/304641-ideas/topic/Roc.20Examples.20-.20migrate.20to.20"Headerless".20Applications/near/576195397>

**Key links**

- <https://github.com/roc-lang/roc/blob/main/docs/langref/types#opaque-types>
- <https://github.com/roc-lang/roc/pull/9206>

**Summary**

Luke Boswell initiated work on migrating Roc examples to "headerless" application modules, drafting an initial PR that includes specific design decisions for the `main!` and `echo!` APIs and a refactor of the CLI frontend pipeline.

**Key points**

- A draft PR was created to introduce header-less app modules.
- The proposed API uses a verbose `Try` signature (`main! : List(Str) => Try({}, [Exit(I32), ..])`) to demonstrate idiomatic error handling in tutorials.
- CLI arguments will be silently sanitized to UTF-8, replacing invalid characters with the unicode replacement character.
- The task scope expanded to include a refactor of the CLI frontend/backend pipeline to clean up logic and improve plugin abstractions.
- A broken link in the documentation regarding opaque types was noted.

**Open questions**

- None explicitly listed, though Luke mentioned making assumptions about the desired API for the tutorial examples.

**Action items**

- Migrate Roc Examples to use the new "headerless" application module format (noted as "Help Wanted").

### roc docs - Generate docs for all modules

- **Channel:** ideas
- **Conversation:** roc docs - Generate docs for all modules
- **Messages:** 4
- **People:** 2
- **Time:** 4:39 PM–4:59 PM (America/Los_Angeles)
- **Participants:** Luke Boswell, Plas
- **Link:** <https://roc.zulipchat.com/#narrow/channel/304641-ideas/topic/roc.20docs.20-.20Generate.20docs.20for.20all.20modules/near/576151827>

**Key links**

- <https://github.com/roc-lang/roc/pull/9174>

**Summary**

Plas requested the ability for roc docs to generate documentation for all imports, platforms, and builtins in a single location. Luke Boswell responded that he has already implemented this functionality in a pending pull request, which generates docs for an application and all its transitive dependencies.

**Key points**

- Currently, there is no single place to view all documentation (imports, platform, builtins) at once.
- A pull request exists that enables generating documentation for all reachable modules.
- The implementation includes documentation for all directly imported packages as well as their transitive dependencies.
- The pull request requires cleanup, a rebase, and HTML polishing before it can be merged.

**Open questions**

- None.

**Action items**

- Luke Boswell to clean up, rebase, and polish the HTML for PR #9174.

### Error: WindowsSDKNotFound

- **Channel:** beginners
- **Conversation:** Error: WindowsSDKNotFound
- **Messages:** 3
- **People:** 2
- **Time:** 2:35 AM–5:15 AM (America/Los_Angeles)
- **Participants:** Daren, Luke Boswell
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/Error.3A.20WindowsSDKNotFound/near/576019751>

**Key links**

- <https://github.com/roc-lang/roc/blob/main/docs/mini-tutorial-new-compiler.md>

**Summary**

A new Roc user on Windows 10 encountered a `WindowsSDKNotFound` linker error when attempting to compile a file, which was resolved by installing the Visual Studio C++ Build Tools.

**Key points**

- The error occurred while following a tutorial on a Windows 10 machine using a debug build of the Roc compiler.
- The linker failed with `WindowsSDKNotFound` when building for the `x64win` target.
- A maintainer suggested installing Visual Studio C++ Build Tools to provide the necessary SDK.
- The user successfully resolved the issue by installing the "C++ desktop development" workload for Visual Studio Community.

**Open questions**

- None.

**Action items**

- None.

### Help Wanted : migrating the Roc Examples

- **Channel:** contributing
- **Conversation:** Help Wanted : migrating the Roc Examples
- **Messages:** 2
- **People:** 2
- **Time:** 11:35 PM–11:36 PM (America/Los_Angeles)
- **Participants:** Luke Boswell, Notification Bot
- **Link:** <https://roc.zulipchat.com/#narrow/channel/316715-contributing/topic/Help.20Wanted.20.3A.20migrating.20the.20Roc.20Examples/near/576195396>

**Key links**

- <https://github.com/roc-lang/roc/issues/9208>
- <https://github.com/roc-lang/examples>
- <https://roc.zulipchat.com/#narrow/channel/316715-contributing/topic/Help.20Wanted.20.3A.20migrating.20the.20Roc.20Examples/near/576195293>

**Summary**

Luke Boswell announces the merge of a header-less app and echo platform into main and requests help migrating the Roc examples to this new structure, proposing a temporary branch to stage changes until the new Zig compiler becomes the default.

**Key points**

- A header-less app / echo platform has been merged into main.
- There is a known bug (#9208) regarding error tags with payloads that have a custom `Str.inspect` implementation, though it is considered rare.
- Migration of examples should be done as a separate branch until the new Zig compiler is the default.
- Examples requiring platforms like basic-cli or webserver should be moved to external examples in their respective repositories.
- Contributors should consult snapshot tests to verify the correct latest syntax.

**Open questions**

- None.

**Action items**

- Migrate examples from the `roc-lang/examples` repository via a new branch.
- Submit one PR per example for the migration.
- Move platform-dependent examples (e.g., basic-cli/webserver) to external repos.

### command line parsing

- **Channel:** beginners
- **Conversation:** command line parsing
- **Messages:** 1
- **People:** 1
- **Time:** 2:55 AM–2:55 AM (America/Los_Angeles)
- **Participants:** Plas
- **Link:** <https://roc.zulipchat.com/#narrow/channel/231634-beginners/topic/command.20line.20parsing/near/575992772>

**Summary**

A user expresses frustration regarding breaking changes in Roc's `Str` or `Result` types and wishes that project authors would specify exact versions of Roc and `basic-cli` they tested with, rather than targeting the "latest version," until the language reaches version 1.0.0.

**Key points**

- The user suspects a recent failure was caused by changes to the `Str` or `Result` types.
- The user acknowledges they are new to Roc and that the language evolves frequently.
- The user advises against using "latest version" for `basic-cli` in projects before Roc reaches stability (v1.0.0).

**Open questions**

- None

**Action items**

- None
