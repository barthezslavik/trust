# 1. Introduction

Trust is a coordination-safe programming language for autonomous systems.

Traditional systems programming languages solve:

* memory safety,
* concurrency safety,
* low-level correctness.

Trust solves a different class of problems:

```text id="hjrrsp"
duplicate execution
invalid workflow transitions
unsafe retries
tool misuse
budget overruns
agent conflicts
distributed coordination failures
```

Modern software is no longer just:

* functions,
* threads,
* memory allocations.

It is:

* workflows,
* agents,
* tools,
* browser sessions,
* distributed queues,
* external APIs,
* long-running execution graphs.

Trust introduces:

```text id="fx1zk8"
workflow safety
capability ownership
causal execution
temporal validity
coordination checking
```

Where Rust asks:

```text id="x0stp5"
is memory access valid?
```

Trust asks:

```text id="rwjqv9"
is this autonomous action valid?
```

