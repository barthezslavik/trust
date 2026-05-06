# 31. Tool Runtime

The Tool Runtime safely executes external tools.

Tools include:

* browsers,
* APIs,
* databases,
* shells,
* LLMs,
* payment systems.

Example:

```trust id="d8w4gm"
tool Browser
tool CRM
tool OpenAI
```

Tool invocation:

```trust id="m1f2zs"
Browser.open("https://example.com")
```

The runtime manages:

* retries,
* timeouts,
* leases,
* concurrency,
* permissions,
* audit logs.

