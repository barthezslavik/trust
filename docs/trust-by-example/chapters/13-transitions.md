# 13. Transitions

Transitions define allowed movement between states.

```trust id="e9x4ou"
Queued -> Running
Running -> Completed
Running -> Failed
```

Transitions may depend on events:

```trust id="6o2s0i"
Running -> Completed on result_saved
Running -> Failed on timeout
```

Invalid transitions are rejected.

Example:

```trust id="y0z7vd"
Completed -> Running
```

Compiler output:

```text id="zw4x7r"
coordination error:
transition from Completed to Running is forbidden
```

Transitions make workflows:

* deterministic,
* analyzable,
* safe to replay.

