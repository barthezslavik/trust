# 15. Flow of Coordination

Traditional flow control manages instructions.

Trust flow control manages autonomous execution.

Example:

```trust id="u5j8bo"
when lead_found
then scrape_website
```

Conditional coordination:

```trust id="v9n1ra"
if lead.score > 80 {
  send_email()
}
```

Parallel execution:

```trust id="7x0s0n"
parallel {
  scrape_linkedin()
  scrape_company_site()
}
```

Waiting for events:

```trust id="jlwm3u"
await payment_confirmed
```

Timeout handling:

```trust id="g2s7gh"
await payment_confirmed
timeout 5.minutes {
  cancel_order()
}
```

Trust flow control is designed for:

* distributed systems,
* long-running execution,
* asynchronous coordination.

