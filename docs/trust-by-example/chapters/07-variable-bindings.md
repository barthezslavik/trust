# 7. Variable Bindings

Bindings in Trust are explicit about ownership and mutability.

```trust id="3ikm3s"
let company = "Acme"
let mut score = 50
```

Trust also introduces execution-aware bindings.

```trust id="0k2g5v"
lease browser: BrowserSession
claim job: Job
```

A lease represents temporary ownership of a runtime resource.

A claim represents exclusive ownership of a coordination object.

Example:

```trust id="y9n6ec"
workflow ScrapeLead {
  lease browser: BrowserSession

  step browser.open("https://example.com")
}
```

Only one workflow may actively own a browser lease at a time.

This prevents:

* session corruption,
* parallel conflicts,
* unsafe execution overlap.

