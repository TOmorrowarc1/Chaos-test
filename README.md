# Chaos Kernel Debugging Homework

## IMPORTANT NOTICE -- READ BEFORE YOU START

**Direct use of LLMs (Large Language Models) to generate your solution is strictly prohibited.**

You are allowed and encouraged to use AI agents (e.g., Cursor Agent, Copilot Chat, etc.) as *tools* during your workflow. However, all submissions must include:

1. **Your complete agent dialogue logs.** Export and attach the full conversation history with any AI agent you used. **Only inline TAB operation can be waived.**
2. **A clear annotation** in your submission indicating which parts of the code were **written by you (human)** and which parts were **generated or suggested by the agent**. You may annotate inline with comments like `// HUMAN` and `// AGENT`, or provide a separate summary document.

**Any violation of this policy -- including but not limited to submitting agent-generated code without disclosure, fabricating dialogue logs, or using an LLM to produce the final solution directly -- will result in a score of zero (0) for the entire assignment.**

The purpose of this policy is to ensure you *understand* the bugs and the code you are fixing. The agent is a collaborator, not a substitute for your own reasoning.

---

## Overview

This project is built on top of the [rCore](https://github.com/rcore-os/rCore) teaching operating system. The file `kernel/src/kernel.rs` contains a monolithic kernel simulation with **intentionally embedded bugs** across multiple subsystems -- locking, memory management, scheduling, file systems, IPC, signal handling, and more. Some bugs cause incorrect behavior at runtime; others prevent compilation entirely.

A comprehensive test suite is provided under `chaos-tests/`.

## Your Tasks

### Task 1: Debug and Pass All Tests

The kernel code in `kernel/src/kernel.rs` contains numerous bugs of varying difficulty.

Your goal is to **find and fix all bugs** so that the entire test suite passes:

```bash
# Run the basic tests
cargo test --test basic

# Run the advanced tests
cargo test --test advanced

# Run the pressure tests
cargo test --test pressure
```

All three test groups must pass for full credit.

> **Clarifications (April 28)**
>
> `chaos-tests/src/lib.rs` is now a symbolic link pointing to `kernel/src/kernel.rs`.
> Therefore, any changes made to the kernel source will automatically be reflected in the test suites.

## Project Structure

```
chaos/
├── kernel/
│   └── src/
│       └── kernel.rs      # The buggy monolithic kernel (YOUR TARGET)
└── README.md                      # This file
```

## Getting Started

1. Try to compile the project first -- fix all compilation errors:
   ```bash
   cargo check
   ```

2. Once it compiles, run the basic tests and fix bugs one group at a time:
   ```bash
   cargo test --test basic -- group_01
   ```

3. Move on to advanced and pressure tests after basic tests pass.

## Grading

| Component | Weight |
|-----------|--------|
| Basic tests passing | 33% |
| Advanced tests passing | 33% |
| Pressure tests passing | 34% |
