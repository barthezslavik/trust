# 35. Retry Semantics

Retries are one of the largest sources of distributed failures.

Trust makes retries explicit.

Example:

```trust id="x4o2jf"
retry 3 times
```

Exponential backoff:

```trust id="f7k3bw"
retry exponential {
  attempts 5
  start 1.second
  max 5.minutes
}
```

Idempotent retry:

```trust id="p6r4zm"
@idempotent
action save_lead()
```

The Trust Checker validates retry safety.

Unsafe example:

```trust id="h2n8yu"
retry charge_customer()
```

Compiler output:

```text id="n7f5ds"
coordination warning:
non-idempotent action retried without compensation flow
```

