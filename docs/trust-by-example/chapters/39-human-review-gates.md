# 39. Human Review Gates

Not all decisions should be autonomous.

Trust allows human approval boundaries.

Example:

```trust id="g1k9wd"
@approval(required: true)
action wire_transfer()
```

Workflow gate:

```trust id="s4x2vo"
await human_review
```

Approval systems may:

* inspect workflows,
* replay execution,
* approve retries,
* override policies.

This allows hybrid human-agent coordination systems.

