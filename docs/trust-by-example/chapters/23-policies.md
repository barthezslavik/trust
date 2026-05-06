# 23. Policies

Policies define operational constraints.

Example:

```trust id="q4h9wb"
policy OutreachPolicy {
  emails_per_day < 100
  require verified_email
}
```

Policies may apply to:

* workflows,
* agents,
* actions,
* organizations.

Example:

```trust id="o7s1lg"
workflow SendCampaign
  follows OutreachPolicy
```

Violations produce coordination errors:

```text id="t5n4mr"
policy violation:
emails_per_day exceeded
```

Policies make governance part of the language itself.

