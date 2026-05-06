# 9. Capabilities

Capabilities define what a workflow or agent is allowed to do.

Traditional systems often rely on:

* runtime checks,
* environment variables,
* hidden permissions.

Trust makes permissions explicit.

```trust id="0y0sm2"
capability SendEmail
capability UseBrowser
capability AccessCRM
```

Agents must declare capabilities:

```trust id="yby9vv"
agent SalesBot {
  can_use [SendEmail, AccessCRM]
}
```

Restricted operations require capabilities.

```trust id="9i9j9k"
fn send_email(to: Email)
  requires SendEmail
```

If a workflow lacks permission:

```text id="k7k9jw"
coordination error:
missing capability SendEmail
```

Capabilities allow:

* sandboxing,
* auditability,
* policy enforcement,
* safe autonomous execution.

