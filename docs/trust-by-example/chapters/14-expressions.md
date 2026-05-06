# 14. Expressions

Expressions in Trust are deterministic and coordination-aware.

Basic expressions:

```trust id="0t4t6l"
let score = leads * 10
```

Policy expressions:

```trust id="3g2g8o"
budget.spent < budget.limit
```

Temporal expressions:

```trust id="r9f5zg"
now() > retry_after
```

Capability expressions:

```trust id="2m4g5x"
agent.has(SendEmail)
```

Invariant expressions:

```trust id="dr4v4q"
no_duplicate_contacts == true
```

Expressions are heavily used in:

* policies,
* retries,
* governance,
* scheduling,
* state validation.

