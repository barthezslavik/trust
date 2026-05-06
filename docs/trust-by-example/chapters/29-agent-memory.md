# 29. Agent Memory

Agent memory stores persistent operational state.

Example:

```trust id="r5n7dv"
memory leads_db: LeadStore
```

Memory may contain:

* workflow history,
* prior actions,
* learned preferences,
* execution summaries.

Trust distinguishes between:

* durable memory,
* temporary memory,
* replay-safe memory.

Temporary memory:

```trust id="c6s0qf"
temp memory session_cache
```

Durable memory:

```trust id="m4o9bx"
durable memory crm_state
```

Memory operations participate in the causality graph.

