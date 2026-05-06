# 16. Time & Durations

Time is a first-class primitive in Trust.

Most coordination failures are temporal failures:

* retries too early,
* expired sessions,
* duplicated jobs,
* stale workflows.

Trust directly models time.

```trust id="1g7g2o"
let timeout: Duration = 30.seconds
let retry_after = 5.minutes
```

Scheduling:

```trust id="6f9r8v"
run workflow Cleanup every 1.hour
```

Expiration:

```trust id="d8l6j2"
lease browser expires in 10.minutes
```

Temporal validity:

```trust id="6l1o9f"
token.valid_until > now()
```

The Trust Checker validates temporal correctness:

* expired leases,
* invalid retries,
* impossible schedules,
* stale actions.

