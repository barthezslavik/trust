# 22. Attributes

Attributes attach metadata and guarantees to workflows and actions.

Example:

```trust id="m9r1tg"
@idempotent
action save_to_crm()
```

Retry-safe action:

```trust id="g4f5oe"
@retryable(max: 3)
action fetch_page()
```

Audit-required action:

```trust id="z1r4jg"
@audit
action charge_customer()
```

Human approval requirement:

```trust id="h8n6qx"
@approval(required: true)
action wire_transfer()
```

Attributes influence:

* runtime behavior,
* governance,
* retries,
* security,
* execution guarantees.

