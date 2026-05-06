# 32. Browser Sessions

Browser sessions are first-class runtime resources.

Example:

```trust id="z5r8ye"
lease browser: BrowserSession
```

Sessions may:

* persist across workflows,
* survive retries,
* maintain cookies and state.

Session ownership prevents conflicts:

```trust id="l2v9mh"
workflow Scraper {
  owns browser: SessionA
}
```

The Trust Checker guarantees:

* no double usage,
* no stale sessions,
* no invalid concurrent execution.

