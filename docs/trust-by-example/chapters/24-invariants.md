# 24. Invariants

Invariants define conditions that must always remain true.

Example:

```trust id="s3z2pq"
invariant {
  no_duplicate_payments
}
```

Workflow invariant:

```trust id="y1v8dx"
workflow Checkout {
  invariant {
    payment.total >= 0
    order.status != Shipped before payment.completed
  }
}
```

The Trust Checker validates invariants:

* during compilation,
* during execution,
* during replay.

Invariant violations are treated as coordination failures.

