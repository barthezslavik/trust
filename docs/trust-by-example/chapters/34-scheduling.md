# 34. Scheduling

Scheduling controls when workflows execute.

Example:

```trust id="s9q2dg"
schedule Cleanup every 1.hour
```

Delayed execution:

```trust id="y5u7lh"
run SendReminder at tomorrow 09:00
```

Conditional scheduling:

```trust id="v3e1rs"
run FollowUp
after payment_completed
```

The runtime guarantees deterministic scheduling behavior across distributed systems.

