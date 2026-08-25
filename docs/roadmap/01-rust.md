# Rust Learning Resource Plan

## What is Rust, and why learn it?

Rust is a statically-typed, compiled systems programming language that guarantees memory
safety and thread safety **without a garbage collector**, using a compile-time ownership
and borrow-checking model. It gives you C/C++-level performance and control (manual memory
layout, zero-cost abstractions, no runtime) with the safety and ergonomics of a modern
language (algebraic data types, pattern matching, a strong type system, excellent tooling
via `cargo`). It has become the language of choice for: OS/embedded/kernel work (Linux
kernel modules, firmware), browser engines and web infrastructure (Servo, Firefox
components), CLI tools (`ripgrep`, `bat`, `fd`, `starship`), high-performance backend
services (via `tokio`/`axum`/`actix-web`), WebAssembly, blockchain/crypto infra, game
engines (`Bevy`), and increasingly AI/ML infra tooling. It is consistently rated the "most
loved language" in Stack Overflow surveys, has a rapidly growing job market, and is a
genuinely different, valuable mental model to learn even if you never ship Rust
professionally — ownership/borrowing changes how you think about memory and concurrency in
every other language too.

This document is a **resource catalog**, not a tutorial. It inventories the best official
docs, courses, books, interactive practice sites, communities, YouTube channels, project
ideas, and tooling for learning Rust from zero to advanced systems/embedded/async work. A
suggested learning order is given at the end.

---

## 1. Official Docs, Books, and Reference Material

All free, all maintained by the Rust Project (`rust-lang`) unless noted.

| Resource | URL | Description | Cost |
|---|---|---|---|
| The Rust Programming Language ("the Book") | https://doc.rust-lang.org/book/ | The canonical introductory book; also in print via No Starch Press. Source at https://github.com/rust-lang/book | Free (paid print/ebook option) |
| Rust Book — interactive Brown University edition | https://rust-book.cs.brown.edu/ | Same book content with embedded interactive quizzes, annotations/highlighting per section — genuinely improves retention vs. the plain book | Free |
| Rust by Example | https://doc.rust-lang.org/rust-by-example/ | Learn via small runnable code snippets covering syntax and stdlib idioms, editable in-browser | Free |
| The Rust Reference | https://doc.rust-lang.org/reference/ | The language specification/reference — precise semantics, not a tutorial | Free |
| The Rustonomicon ("the Nomicon") | https://doc.rust-lang.org/nomicon/ | The advanced/unsafe Rust guide — raw pointers, `Send`/`Sync`, FFI, undefined behavior | Free |
| Asynchronous Programming in Rust ("the Async Book") | https://rust-lang.github.io/async-book/ | Official guide to `async`/`await`, futures, executors, pinning | Free |
| The Embedded Rust Book | https://docs.rust-embedded.org/book/ | Official guide to bare-metal/microcontroller Rust (`no_std`, HALs, PACs) | Free |
| Rust Embedded Discovery Book (microbit / STM32F3) | https://docs.rust-embedded.org/discovery/ (and microbit variant) | Gentler, hardware-in-hand intro to embedded before the main Embedded Book, for people new to embedded generally | Free |
| The Embedonomicon | https://docs.rust-embedded.org/embedonomicon/ | Deep dive on what actually happens getting Rust running on bare metal (linker scripts, runtime init) | Free |
| The Cargo Book | https://doc.rust-lang.org/cargo/ | Official manual for Cargo (Rust's build tool/package manager) | Free |
| The rustdoc Book | https://doc.rust-lang.org/rustdoc/ | How to write and generate API docs with `cargo doc` / `rustdoc` | Free |
| The rustup Book | https://rust-lang.github.io/rustup/ | Toolchain installer/version manager guide | Free |
| The rustc Book | https://doc.rust-lang.org/rustc/ | Compiler flags/usage reference | Free |
| The Edition Guide | https://doc.rust-lang.org/edition-guide/ | What changed across Rust editions (2015/2018/2021/2024) | Free |
| Rust RFC Book | https://rust-lang.github.io/rfcs/ | Archive of accepted RFCs — how/why language features were designed the way they were | Free |
| Unsafe Code Guidelines Reference | https://rust-lang.github.io/unsafe-code-guidelines/ | Precise rules for writing correct `unsafe` code | Free |
| std library docs | https://doc.rust-lang.org/std/ | The standard library API reference — used constantly, day to day | Free |
| Rust API Guidelines | https://rust-lang.github.io/api-guidelines/ | Official checklist + rationale for designing idiomatic, ergonomic public Rust APIs | Free |
| Rust Design Patterns book (unofficial but community-canonical) | https://rust-unofficial.github.io/patterns/ | Idioms, design patterns, and anti-patterns catalog for Rust | Free |
| "100 Exercises to Learn Rust" (Mainmatter / Luca Palmieri) | https://rust-exercises.com/100-exercises/ (repo: https://github.com/mainmatter/100-exercises-to-learn-rust) | A structured, exercise-driven zero-to-intermediate course covering the whole language plus ecosystem basics | Free |
| Google Comprehensive Rust | https://google.github.io/comprehensive-rust/ | Google's 3-4 day internal Rust course, made public; covers basics through generics, error handling, unsafe, and a "Bare Metal" + Android sections | Free |
| Rust Cookbook (community-maintained "rust-lang-nursery" style cookbook) | https://rust-lang-nursery.github.io/rust-cookbook/ | Task-oriented recipes ("how do I parse a URL", "how do I hash a file") mapped to crates | Free |

---

## 2. Best Websites / Blogs / Newsletters for Staying Current

| Resource | URL | Description | Cost |
|---|---|---|---|
| This Week in Rust | https://this-week-in-rust.org/ | The flagship weekly Rust newsletter — updates, CFPs, crate releases, RFC/compiler progress | Free |
| The Rust Blog (official) | https://blog.rust-lang.org/ | Official release announcements and project-wide updates | Free |
| Inside Rust Blog | https://blog.rust-lang.org/inside-rust/ | Behind-the-scenes posts from compiler/lang/infra teams | Free |
| pretzelhammer's Rust blog | https://github.com/pretzelhammer/rust-blog | Widely recommended deep-dive essays (lifetimes, generics, common misconceptions) | Free |
| fasterthanlime blog | https://fasterthanli.me/ | High-quality, entertaining deep dives on async, linking, cross-compilation, and Rust internals | Free |
| Read Rust | https://readrust.net/ | Aggregator/curated feed of notable Rust blog posts across the community | Free |
| corrode.dev blog | https://corrode.dev/blog/ | Rust consultancy blog with practical production-Rust advice (async pitfalls, error handling, hiring) | Free |
| Amos/fasterthanlime & "a-a-ron" style deep technical write-ups, plus Without Boats | https://without.boats/ | Deep language-design essays from a former Rust lang team member (async, pin, generators) | Free |
| Rust Users Forum announcements + "official blog" tag | https://users.rust-lang.org/c/announcements/7 | Where crate authors and the project post release/community announcements | Free |
| blessed.rs | https://blessed.rs/ | Unofficial curated guide to "which crate should I use for X" across categories (serde, tokio, reqwest, axum, sqlx, etc.) — essential ecosystem map | Free |
| Awesome Rust list | https://github.com/rust-unofficial/awesome-rust | The master curated list of Rust frameworks/libraries/resources, kept current | Free |
| r/rust "This Month/Week in Rust" community roundups | https://www.reddit.com/r/rust/ | Community pulse — see Communities section below | Free |

---

## 3. Free Courses (Structured, Multi-Lesson)

| Resource | URL | Description | Cost |
|---|---|---|---|
| Google Comprehensive Rust | https://google.github.io/comprehensive-rust/ | Multi-day structured course, slides + exercises, includes Android/bare-metal/unsafe modules | Free |
| Microsoft "Take your first steps with Rust" (Learn path) | https://learn.microsoft.com/en-us/training/paths/rust-first-steps/ | 11-module structured learning path: setup, ownership, error handling, generics, modules, testing, a CLI capstone | Free |
| Microsoft "Beginner's Series to Rust" (35-part video series) | https://learn.microsoft.com/en-us/shows/beginners-series-to-rust/ | 35 short videos targeted at devs who know another language already; companion repo at https://github.com/microsoft/beginners-series-rust | Free |
| Duke University — Rust Fundamentals (Coursera) | https://www.coursera.org/learn/rust-fundamentals | University-produced beginner course; free to audit (paid certificate) | Free to audit / paid certificate |
| Aalto/FITech MOOC — "Modern and Emerging Programming Languages: Rust" | https://opin.fi/en/study-options/Aalto/fitech-mooc-modern-and-emerging-programming-languages-rust/ | Free self-paced Finnish university MOOC covering Rust basics, memory safety, concurrency | Free |
| Tour of Rust | https://tourofrust.com/ | Bite-sized interactive step-by-step tour of the language in-browser, available in many languages | Free |
| "100 Exercises to Learn Rust" | https://rust-exercises.com/100-exercises/ | Structured exercise course, ~100 exercises with a companion `solutions` branch | Free |
| Rustlings | https://rustlings.rust-lang.org/ (repo: https://github.com/rust-lang/rustlings) | Official small-exercises CLI workshop with watch mode and progress tracking — the standard "first week" companion to the Book | Free |
| Codecademy "Rust for Programmers" | https://www.codecademy.com/learn/rust-for-programmers | Interactive browser course aimed at experienced programmers moving into Rust | Free |
| JetBrains Academy — Rust course(s) | https://academy.jetbrains.com/course/27805 (100 exercises variant) and other JetBrains Rust tracks | Structured, IDE-integrated (RustRover) exercise courses | Free / some paid tracks |
| Rust Programming for Beginners — freeCodeCamp / YouTube full courses | e.g. https://www.youtube.com/watch?v=zF34dRivLOw (freeCodeCamp "Rust Programming Course for Beginners") | Long-form single-video full courses, good for a linear watch-through | Free |

---

## 4. Paid Courses / Books Worth Calling Out

All labeled **PAID**.

| Resource | URL | Description | Cost |
|---|---|---|---|
| **Zero To Production In Rust** (Luca Palmieri) | https://www.zero2prod.com/ | The definitive "build a real backend/API in Rust" book — email newsletter service built end-to-end with `actix-web`/`axum`, sqlx, testing, CI, deployment. Extremely well regarded for backend/web Rust | Paid (ebook) |
| **Rust for Rustaceans** (Jon Gjengset, No Starch Press) | https://nostarch.com/rust-rustaceans | The standard "intermediate → advanced idiomatic Rust" book: traits, generics, error design, unsafe, macros, project structure, API design | Paid |
| **Programming Rust, 2nd Ed.** (Jim Blandy, Jason Orendorff, Leonora Tindall — O'Reilly) | https://www.oreilly.com/library/view/programming-rust-2nd/9781492052586/ | Comprehensive, systems-oriented reference-style Rust book; go-to alternative/companion to the official Book for deeper coverage | Paid |
| **Async Rust** (Flitton & Morton, O'Reilly) | https://www.oreilly.com/library/view/async-rust/9781098149086/ | Book-length treatment of async runtimes, Tokio internals, actors, testing async code, custom executors | Paid |
| **Rust Atomics and Locks** (Mara Bos, O'Reilly) | https://marabos.nl/atomics/ | Free to read online (also sold in print) — the best resource on low-level concurrency primitives, memory ordering, building your own mutex/lock | Free online / Paid print |
| **The Rust Programming Language, 3rd Ed.** print edition | https://nostarch.com/rust-programming-language-3e | Print/ebook edition of the official free-online Book, for those who prefer paper | Paid (content free online) |
| Ardan Labs "Certified Rust" exam/training | https://www.ardanlabs.training/ | Structured paid training + a proctored certification exam (100 Q, 90 min, 80% pass, 2-yr validity) — see Certifications section | Paid |
| Linux Foundation LFD480 — "Programming in Rust" | https://training.linuxfoundation.org/training/programming-in-rust-lfd480/ | Instructor-style Linux Foundation training course for experienced developers moving to Rust | Paid |
| Manning "Embedded Software with Rust" / "Embedded Systems with Rust" (liveBooks) | https://www.manning.com/books/embedded-software-with-rust | Paid, embedded-focused Rust books | Paid |

---

## 5. Interactive Labs / Sandboxes / Playgrounds

| Resource | URL | Description | Cost |
|---|---|---|---|
| Rust Playground (official) | https://play.rust-lang.org/ | Run/share Rust snippets in-browser, no install; can show generated LLVM IR / ASM / MIR | Free |
| Rustlings | https://rustlings.rust-lang.org/ | Local CLI-based guided exercises with instant test feedback and watch mode | Free |
| Exercism — Rust Track | https://exercism.org/tracks/rust (repo: https://github.com/exercism/rust) | ~99 exercises, download-solve-submit workflow, optional human mentoring | Free |
| Rustfinity | https://www.rustfinity.com/ | Browser-based Rust "playground + challenges" site with a coding-challenge track | Free (some premium features) |
| LabEx Rust tutorials | https://labex.io/tutorials/rust-online-rust-playground-372918 and related LabEx Rust skill tracks | Guided hands-on browser labs with real sandboxed environments for specific Rust skills | Free/paid tiers |
| Codewars — Rust kata | https://www.codewars.com/kata/search/rust | Kata-style bite-sized challenges with community solutions/discussion, good for algorithmic practice | Free (paid for some features) |
| CodeCrafters "Build Your Own X" (Redis, Git, Shell, HTTP server, Docker, Grep, etc.) — Rust track | https://codecrafters.io/ (community Rust repos e.g. https://github.com/lmammino/codecrafters-redis) | Guided, staged systems-programming challenges — build a real Redis/Git/interpreter from scratch, testable against real clients | Free tier + paid tracks |
| Advent of Code | https://adventofcode.com/ | Annual December puzzle set; huge community of Rust solutions to study (search GitHub "advent-of-code rust") | Free |
| Google Comprehensive Rust in-browser exercises | https://google.github.io/comprehensive-rust/exercises.html | Exercises embedded directly in the course, runnable via mdBook playground integration | Free |

---

## 6. GitHub Repos Worth Studying or Cloning

### Awesome-lists / curated indexes
| Resource | URL | Description | Cost |
|---|---|---|---|
| rust-unofficial/awesome-rust | https://github.com/rust-unofficial/awesome-rust | THE master curated list of Rust frameworks, libraries, and resources | Free |
| rust-embedded/awesome-embedded-rust | https://github.com/rust-embedded/awesome-embedded-rust | Curated list specific to embedded/low-level Rust | Free |
| mjovanc/awesome-tokio | https://github.com/mjovanc/awesome-tokio | Curated list of Tokio-ecosystem crates and examples | Free |
| nicoburns/blessed-rs (source of blessed.rs) | https://github.com/nicoburns/blessed-rs | Crate recommendation guide, browsable as a repo | Free |

### Exercise / learning repos
| Resource | URL | Description | Cost |
|---|---|---|---|
| rust-lang/rustlings | https://github.com/rust-lang/rustlings | Source of the Rustlings exercises | Free |
| mainmatter/100-exercises-to-learn-rust | https://github.com/mainmatter/100-exercises-to-learn-rust | Source of the "100 Exercises" course | Free |
| exercism/rust | https://github.com/exercism/rust | Source of the Exercism Rust track exercises | Free |
| rust-lang/rust-by-example | https://github.com/rust-lang/rust-by-example | Source of Rust by Example | Free |
| microsoft/beginners-series-rust | https://github.com/microsoft/beginners-series-rust | Companion code for Microsoft's beginner video series | Free |

### Production-grade codebases good for reading
| Resource | URL | Description | Cost |
|---|---|---|---|
| BurntSushi/ripgrep | https://github.com/BurntSushi/ripgrep | Widely recommended as a model of fast, well-tested, well-documented application Rust (CLI design, error handling, perf) | Free |
| rust-lang/regex | https://github.com/rust-lang/regex | Extremely rigorously engineered library crate; great for API design + testing discipline | Free |
| tokio-rs/tokio | https://github.com/tokio-rs/tokio | The dominant async runtime; excellent for concurrency/async architecture patterns at scale | Free |
| tokio-rs/axum | https://github.com/tokio-rs/axum | Modern, ergonomic web framework built on Tokio/Hyper/Tower — good example of trait-based extensible API design | Free |
| quickwit-oss/tantivy | https://github.com/quickwit-oss/tantivy | Full-text search library; praised as a best-practices example of a serious library crate | Free |
| servo/servo | https://github.com/servo/servo | Large-scale, real browser engine — great for studying huge multi-crate architecture | Free |
| rust-lang/rust | https://github.com/rust-lang/rust | The compiler + stdlib itself — advanced language use and compiler engineering at the extreme end | Free |
| bevyengine/bevy | https://github.com/bevyengine/bevy | Modern ECS game engine; good example of plugin architecture and macro-heavy ergonomic API design | Free |
| zed-industries/zed | https://github.com/zed-industries/zed | Large modern GUI application (code editor) written in Rust; real-world async + GPU + UI architecture | Free |
| pola-rs/polars | https://github.com/pola-rs/polars | High-performance DataFrame library; great for studying performance-oriented API design | Free |
| nushell/nushell | https://github.com/nushell/nushell | Structured-data shell; good for studying parsers, pipelines, and CLI UX in Rust | Free |
| sharkdp/bat, sharkdp/fd, starship/starship | https://github.com/sharkdp/bat, https://github.com/sharkdp/fd, https://github.com/starship/starship | Smaller, very readable, beginner-friendly production CLI tools — good "second codebase to read" after ripgrep | Free |

### Starter templates / scaffolding
| Resource | URL | Description | Cost |
|---|---|---|---|
| cargo-generate/cargo-generate | https://github.com/cargo-generate/cargo-generate | Tool to scaffold new Rust projects from any GitHub template repo (`cargo generate user/template`) | Free |
| cargo-generate template list | https://github.com/cargo-generate/cargo-generate/blob/main/TEMPLATES.md | Curated list of community project templates (CLI, web, embedded, WASM, game) | Free |
| leptos-rs/start-axum, leptos-rs/start-trunk | https://github.com/leptos-rs/start-axum, https://github.com/leptos-rs/start-trunk | Official starter templates for the Leptos full-stack Rust web framework | Free |

---

## 7. Forums / Communities

| Resource | URL | Description | Cost |
|---|---|---|---|
| Official Rust Users Forum | https://users.rust-lang.org/ | The primary official Q&A/discussion forum — best place for "why won't this compile" and design questions | Free |
| Internals forum (compiler/lang design) | https://internals.rust-lang.org/ | Where language/compiler RFCs and pre-RFCs are discussed by contributors | Free |
| r/rust | https://www.reddit.com/r/rust/ | The main Rust subreddit — news, show-and-tell, weekly "Hey Rustaceans, got a question?" thread | Free |
| r/learnrust | https://www.reddit.com/r/learnrust/ | Beginner-focused subreddit, lower-stakes questions welcome | Free |
| Official Rust Discord | https://discord.gg/rust-lang (linked from https://www.rust-lang.org/community) | Real-time chat, official community server | Free |
| Rust Zulip | https://rust-lang.zulipchat.com/ | Where a lot of official team/working-group discussion happens (compiler, lang, async, embedded WGs each have streams) | Free |
| Rust embedded Matrix/Discord community | linked from https://www.rust-embedded.org/ and the Embedded Book | Community chat specifically for embedded/`no_std` Rust | Free |
| Exercism Rust track forum | https://forum.exercism.org/ (tag: rust) | Track-specific mentoring/discussion for Exercism exercises | Free |
| This Week in Rust community calendar / working groups | https://this-week-in-rust.org/ | Lists community meetings/working-group calls you can join | Free |
| Rust user groups (local meetups) | https://www.meetup.com/topics/rust/ | In-person/virtual local Rust meetups worldwide | Free |

---

## 8. YouTube Channels

| Channel | URL | Description | Cost |
|---|---|---|---|
| Let's Get Rusty | https://www.youtube.com/@letsgetrusty | The most-recommended beginner channel; follows the official Book chapter-by-chapter plus standalone concept videos | Free |
| Jon Gjengset | https://www.youtube.com/@jonhoo | Long-form, deep, "watch me build/explain real systems" streams — the top pick once past basics; covers async internals, unsafe, crate deep-dives | Free |
| fasterthanlime (video content) | https://www.youtube.com/@fasterthanlime | Entertaining, technically deep videos on linking, cross-compilation, async, and Rust internals | Free |
| Tensor Programming | https://www.youtube.com/@TensorProgramming | Structured tutorial series covering language fundamentals and specific topics (traits, generics, error handling) | Free |
| Official Rust YouTube channel | https://www.youtube.com/@rust_lang | RustConf and other official talks | Free |
| Chris Biscardi | https://www.youtube.com/@chrisbiscardi | Practical Rust + WASM + web content, project-based | Free |
| Ryan Levick (ex Rust lang team, Microsoft) | https://www.youtube.com/@RyanLevicksVideos and his Microsoft Beginner Series appearances | Approachable explanations of ownership, traits, and async | Free |
| No Boilerplate | https://www.youtube.com/@NoBoilerplate | Short, high-production-value "why Rust" and ecosystem-overview videos, good for motivation/orientation | Free |
| RustConf / EuroRust / RustFest recorded talks | https://www.youtube.com/results?search_query=rustconf, https://www.youtube.com/@eurorust | Conference-talk archives — great for advanced/niche topics (async runtimes, unsafe, embedded, WASM) | Free |

---

## 9. Practice Project Ideas (Beginner → Advanced)

### Beginner (fundamentals: ownership, structs/enums, error handling, collections)
- CLI calculator / unit converter / tip splitter
- Number-guessing game
- To-do list app (in-memory, then file-persisted with `serde` + JSON)
- Simple Mad Libs / text adventure game
- Temperature/currency converter with `clap` for argument parsing
- Word/line/character counter (a "wc" clone)
- Basic Markdown-to-HTML converter

### Intermediate (traits/generics, iterators, concurrency basics, testing)
- `grep` clone (pattern search over files) — mirrors the official Book's final project
- `cat`/`ls`/`cut`/`sort` clones — the classic "coreutils in Rust" exercise set (see `uutils/coreutils` for reference)
- A key-value store with a simple on-disk log (mini-database, e.g. following "Build Your Own Database")
- Multi-threaded web scraper or file-hasher using `std::thread`/channels, then rewritten with `rayon`
- A JSON/CSV parser written from scratch (no `serde`) to understand parsing and error types
- A simple HTTP server from raw TCP sockets (no framework) — understand what `axum`/`actix` abstract away
- A URL shortener or pastebin REST API using `axum` + `sqlx`/`diesel` + Postgres
- A chat server using `tokio` + WebSockets

### Advanced (systems/async/embedded/WASM)
- Build your own Redis server (CodeCrafters "Build Your Own Redis", Rust track) — RESP parsing, expiry, replication
- Build your own Git (CodeCrafters "Build Your Own Git") — object storage, plumbing commands
- Build a toy async runtime/executor from scratch (following the Async Book's "Applied: Build an Executor")
- Write a custom allocator or arena allocator (`unsafe`, raw pointers)
- Build a simple bytecode VM or interpreter for a toy language (great `enum`/pattern-matching showcase)
- Port a small game or app to WebAssembly with `wasm-bindgen`/`wasm-pack`, run it in-browser
- Blink an LED / read a sensor on real hardware with the Embedded Book + a `microbit` or STM32/ESP32 dev board; graduate to a `no_std` firmware project (e.g. RTIC or Embassy async embedded framework)
- Build a small game with the Bevy ECS engine (2D platformer or Pong clone)
- Contribute a small fix/feature to a real crate from the "codebases to read" list above (ripgrep, bat, fd, etc.) as a capstone

---

## 10. Certification Paths

There is **no official Rust Foundation / Rust Project certification** — the language has
no vendor-run "certified developer" exam analogous to Oracle Java or AWS certs. The closest
available options:

| Resource | URL | Description | Cost |
|---|---|---|---|
| Ardan Labs "Certified Rust" | https://www.ardanlabs.training/ | Proctored exam: 100 questions, 90 minutes, 80% pass threshold, 2-year validity. The closest thing to a recognized third-party Rust certification | Paid |
| Linux Foundation LFD480 "Programming in Rust" | https://training.linuxfoundation.org/training/programming-in-rust-lfd480/ | Training-completion course (not a language certification exam) aimed at experienced developers | Paid |
| Coursera course-completion certificates (Duke Rust Fundamentals, Rust specializations) | https://www.coursera.org/learn/rust-fundamentals | Certificate of completion, not an independent certification body | Paid (for the certificate; auditing is free) |
| CodeSignal / Coddy Rust skill certificates | https://codesignal.com/, https://coddy.tech/certification/rust | Skill-verification certificates from coding-assessment platforms, useful as portfolio signal rather than an industry-standard credential | Free/paid |

**Practical takeaway:** for most purposes, a portfolio of real projects (see §9) and
contributions to open-source Rust crates carries far more weight in hiring than any
existing "certification."

---

## 11. Tooling / Ecosystem Resources

| Tool | URL | Description | Cost |
|---|---|---|---|
| rustup | https://rust-lang.github.io/rustup/ | Official toolchain installer/version manager — the standard way to install Rust | Free |
| Cargo | https://doc.rust-lang.org/cargo/ | Official build tool, package manager, and test runner; the center of the whole workflow | Free |
| rustfmt | https://github.com/rust-lang/rustfmt | Official code formatter (`cargo fmt`) | Free |
| Clippy | https://doc.rust-lang.org/clippy/ | Official linter catching idiomatic mistakes and common bugs (`cargo clippy`) | Free |
| rust-analyzer | https://rust-analyzer.github.io/ | The standard Language Server Protocol implementation powering IDE support (VS Code, Neovim, etc.) | Free |
| Miri | https://github.com/rust-lang/miri | Interpreter that detects undefined behavior in `unsafe` code paths (`cargo +nightly miri test`) | Free |
| cargo-expand | https://github.com/dtolnay/cargo-expand | Shows what macros/derives actually expand to — essential when debugging macro-heavy code | Free |
| cargo-generate | https://github.com/cargo-generate/cargo-generate | Scaffold new projects from GitHub templates | Free |
| cargo-audit / cargo-deny | https://github.com/RustSec/cargo-audit, https://github.com/EmbarkStudios/cargo-deny | Dependency vulnerability/license/policy auditing against the RustSec advisory database | Free |
| cargo-watch | https://github.com/watchexec/cargo-watch | Re-run build/test/run on file change | Free |
| cargo-nextest | https://nexte.st/ | Faster, better-UX test runner replacement for `cargo test` | Free |
| crates.io | https://crates.io/ | The official Rust package registry; browse by category (`https://crates.io/categories`) — e.g. `command-line-utilities`, `asynchronous`, `web-programming`, `embedded`, `wasm`, `game-development`, `cryptography` | Free |
| docs.rs | https://docs.rs/ | Auto-generated, hosted documentation for every crate published to crates.io | Free |
| blessed.rs | https://blessed.rs/ | Curated "which crate should I pick" guide across ecosystem categories | Free |
| Tokio | https://tokio.rs/ | The dominant async runtime; site includes its own excellent tutorial | Free |
| Bevy | https://bevy.org/ | Free, open-source, ECS-based game engine and its official Quick Start guide | Free |
| wasm-bindgen / wasm-pack | https://rustwasm.github.io/docs/wasm-bindgen/, https://rustwasm.github.io/docs/wasm-pack/ | The standard toolchain bridging Rust and JavaScript for WebAssembly | Free |
| Playground compiler-explorer features | https://play.rust-lang.org/ | View generated ASM/LLVM-IR/MIR directly from source without local setup | Free |

---

## 12. Cheat Sheets / Quick References / Roadmaps

| Resource | URL | Description | Cost |
|---|---|---|---|
| roadmap.sh Rust roadmap | https://roadmap.sh/rust (PDF: https://roadmap.sh/pdfs/roadmaps/rust.pdf) | Visual topic-by-topic roadmap from setup through concurrency and testing | Free |
| cheats.rs | https://cheats.rs/ | Extremely detailed, visually organized Rust language cheat sheet (also as PDF) — probably the single best quick-reference | Free |
| Rust quickref (quickref.me) | https://quickref.me/rust.html | Compact single-page syntax cheat sheet | Free |
| OpenSource.com Rust cheat sheet | https://opensource.com/downloads/rust-cheat-sheet | Printable 2-page PDF reference | Free |
| Zero To Mastery Rust cheat sheet | https://zerotomastery.io/cheatsheets/rust-cheat-sheet/ | Beginner-friendly condensed reference | Free |
| Comprehensive Rust course slides (as a reference) | https://google.github.io/comprehensive-rust/ | Doubles as a fast topic-by-topic refresher once you've done a first pass | Free |

---

## Suggested Learning Progression

**Phase 0 — Setup (Day 1)**
1. Install via `rustup` (https://rust-lang.github.io/rustup/). Set up `rust-analyzer` + Clippy + rustfmt in your editor.
2. Skim `cheats.rs` and the roadmap.sh Rust roadmap just to see the shape of the whole language up front.

**Phase 1 — Beginner (Weeks 1-3)**
1. Work through *The Rust Programming Language* (prefer the Brown interactive edition for the quizzes) chapter by chapter.
2. In parallel, do **Rustlings** exercises matching each chapter, and watch the corresponding **Let's Get Rusty** videos as reinforcement.
3. Use **Rust by Example** and **Tour of Rust** as quick-reference side reading.
4. Build 3-4 Beginner project ideas from §9 as you finish relevant chapters (ownership → to-do list; error handling → file-backed notes app; traits/generics → small library).

**Phase 2 — Solidifying fundamentals (Weeks 4-6)**
1. Complete **"100 Exercises to Learn Rust"** (Mainmatter) or the **Exercism Rust track** for broader, less book-guided practice.
2. Read the **Rust API Guidelines** and **Rust Design Patterns** book to start writing idiomatic (not just working) Rust.
3. Build 2-3 Intermediate projects: a `grep`/coreutils clone, a small REST API with `axum`, a multithreaded CLI tool with `rayon`.
4. Start reading a well-regarded production codebase, e.g. **ripgrep** or **bat**, alongside your own writing.

**Phase 3 — Specialize (Weeks 7-12+, pick your track(s))**
- **Backend/web:** *Zero To Production in Rust* (paid book) end to end; study `axum`/`tokio` source; read `blessed.rs` for the surrounding crate ecosystem (serde, sqlx, tower).
- **Async/concurrency depth:** the official *Asynchronous Programming in Rust* book → Tokio's own tutorial (https://tokio.rs/tokio/tutorial) → *Rust Atomics and Locks* (free online) → build a toy executor.
- **Systems/advanced idiomatic Rust:** *Rust for Rustaceans* (paid book) → the Rustonomicon → Jon Gjengset's YouTube deep-dives → contribute a fix to a real crate.
- **Embedded:** The Embedded Rust Book → Discovery Book (with a microbit/STM32 board) → Embedonomicon → build a real firmware project with RTIC or Embassy.
- **WASM:** MDN's Rust-to-Wasm guide → the wasm-bindgen guide's Game of Life tutorial → ship a small interactive web widget compiled from Rust.
- **Game dev:** Bevy's official Quick Start → build a Pong/platformer clone → study Bevy's own source for ECS patterns.

**Phase 4 — Advanced capstones (ongoing)**
1. Do CodeCrafters "Build Your Own Redis" and/or "Build Your Own Git" for a serious systems-programming capstone with real protocol/format fidelity.
2. Read/annotate a large codebase end-to-end (Tokio, Servo, or the Rust compiler itself) for architecture lessons.
3. Join the community: subscribe to **This Week in Rust**, lurk on the **Rust Zulip**/**Discord**, answer beginner questions on **r/learnrust** or the **Users Forum** — teaching is one of the fastest ways to cement mastery.
4. Consider the **Ardan Labs certification** if you want an external credential, but prioritize a portfolio of real projects and any open-source contributions over the exam itself.
