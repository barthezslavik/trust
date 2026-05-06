# 38. Failure Handling

Failures are first-class execution events.

Example:

```trust id="q8w0ru"
on failure {
  retry 3
  then human_review
}
```

Failure categories:

* temporal,
* capability,
* network,
* policy,
* causality,
* invariant violations.

Example:

```trust id="u5e3mc"
on timeout {
  release_browser()
}
```

Trust systems are designed to fail predictably rather than catastrophically.

