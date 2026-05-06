# 33. Queues

Queues coordinate distributed execution.

Example:

```trust id="b7x1po"
queue LeadQueue
```

Producing jobs:

```trust id="m0c3tw"
enqueue LeadQueue <- lead
```

Consuming jobs:

```trust id="e4k8aj"
claim LeadQueue -> job
```

Claims are exclusive.

This prevents:

* duplicate workers,
* race conditions,
* parallel corruption.

Queues are deeply integrated with:

* workflows,
* retries,
* scheduling,
* replay systems.

