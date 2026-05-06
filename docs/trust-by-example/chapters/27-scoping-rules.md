# 27. Scoping Rules

Scopes control visibility and ownership boundaries.

Example:

```trust id="l8o3eg"
workflow ProcessLead {
  let score = 90
}
```

`score` exists only inside the workflow scope.

Trust also introduces operational scopes:

```trust id="s2j6bw"
scope finance {
  capability WireTransfer
}
```

Capability scopes prevent privilege leakage.

Budget scopes:

```trust id="e4v7nu"
scope outreach {
  budget <$50/day
}
```

Scopes may apply to:

* workflows,
* agents,
* organizations,
* execution domains.

They are fundamental for safe autonomous coordination.

