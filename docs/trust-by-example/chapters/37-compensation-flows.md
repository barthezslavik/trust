# 37. Compensation Flows

Some actions cannot be truly reversed.

Trust uses compensation flows for recovery.

Example:

```trust id="v6n1ej"
compensate {
  send_apology_email()
}
```

Compensation differs from rollback:

* rollback restores state,
* compensation mitigates effects.

Used heavily in:

* payments,
* logistics,
* human workflows,
* external systems.

