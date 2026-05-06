# 17. Functions

Functions encapsulate reusable logic.

```trust id="x0m4qw"
fn calculate_score(visits: Int) -> Int {
  visits * 10
}
```

Trust distinguishes between:

* pure functions,
* coordination functions,
* external actions.

Pure functions:

```trust id="j6v2pi"
pure fn normalize(text: String) -> String
```

Pure functions:

* have no side effects,
* are deterministic,
* are replay-safe.

Coordination functions:

```trust id="ql4s8f"
fn reserve_browser() -> BrowserSession
```

These interact with runtime resources.

