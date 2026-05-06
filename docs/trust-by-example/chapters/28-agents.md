# 28. Agents

Agents are autonomous execution entities in Trust.

Unlike ordinary services, agents:

* make decisions,
* coordinate tools,
* manage workflows,
* consume resources,
* operate over time.

Example:

```trust id="q1m8wo"
agent SalesBot {
  can_use [Browser, CRM, Email]
}
```

Agents may own:

* capabilities,
* memory,
* budgets,
* leases,
* workflows.

Agents are first-class runtime objects.

