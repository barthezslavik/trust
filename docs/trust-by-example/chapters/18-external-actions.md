# 18. External Actions

External actions affect the outside world.

Examples:

* sending emails,
* charging cards,
* opening browsers,
* writing to CRMs.

Trust treats them specially because they are:

* non-deterministic,
* expensive,
* dangerous,
* irreversible.

Example:

```trust id="9u6v5f"
action send_email(to: Email)
```

Actions may require:

* capabilities,
* budgets,
* audit logging,
* human approval.

Example:

```trust id="t7g5qw"
action charge_customer(amount: Money)
  requires PaymentCapability
  audit
```

External actions are tracked in the causality graph:

```text id="5f8o8v"
workflow CheckoutFlow
-> action charge_customer
-> event payment_completed
```

This makes distributed systems observable and replayable.

