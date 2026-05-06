# 10. States

Trust systems are stateful by nature.

Traditional software often hides state transitions implicitly.

Trust models them directly.

```trust id="vij0qg"
state Queued
state Running
state Completed
state Failed
```

States belong to workflows, agents, and resources.

Example:

```trust id="g9n4d8"
workflow PaymentFlow {
  state Created
  state Authorized
  state Charged
  state Refunded
}
```

States are not labels.

They are enforced coordination boundaries.

This means:

* invalid transitions are impossible,
* retries become predictable,
* workflows become replayable.

