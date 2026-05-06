# 11. Events

Events describe changes in the system.

```trust id="z0t7yy"
event payment_received
event browser_opened
event lead_scored
```

Events are immutable and causally tracked.

Example:

```trust id="92i2jo"
when payment_received
then start_shipping
```

Every event contains:

* timestamp,
* source workflow,
* causality chain,
* execution metadata.

Example runtime log:

```text id="z4t2zg"
[event]
name: payment_received
caused_by: workflow CheckoutFlow
timestamp: 2026-05-07T12:01:55Z
```

Events form the backbone of:

* replay systems,
* audit logs,
* workflow orchestration,
* distributed coordination.

