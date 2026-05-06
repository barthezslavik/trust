# 8. Ownership & Leases

Ownership in Trust extends beyond memory.

Rust introduced memory ownership.

Trust introduces coordination ownership.

Examples of ownable resources:

* browser sessions,
* API quotas,
* workflow locks,
* GPU slots,
* agent permissions,
* budgets,
* external accounts.

Example:

```trust id="qkz7iy"
owns browser: BrowserSession
owns budget: DailyBudget<$50>
```

Resources may also be borrowed temporarily.

```trust id="m0f6e9"
borrow queue: JobQueue
```

Or leased with expiration:

```trust id="z3h3j2"
lease browser for 10.minutes
```

The Trust Checker validates:

* no double ownership,
* no use-after-release,
* no invalid concurrent usage.

Example violation:

```trust id="zv2r0v"
workflow A {
  owns browser: Session1
}

workflow B {
  owns browser: Session1
}
```

Compiler output:

```text id="jl22q4"
coordination error:
BrowserSession(Session1) already owned by workflow A
```

