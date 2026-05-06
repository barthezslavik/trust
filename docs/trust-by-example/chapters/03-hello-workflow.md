# 3. Hello Workflow

The simplest Trust program is a workflow.

```trust id="4wls05"
workflow Hello {
  step print("hello trust")
}
```

A workflow is:

* deterministic,
* replayable,
* observable,
* causally tracked.

Unlike a traditional function:

* workflows may span minutes, hours, or days,
* workflows may survive process crashes,
* workflows may coordinate distributed systems.

Executing a workflow:

```text id="q5u7wg"
trust run hello.trust
```

Output:

```text id="kl7xg9"
[workflow:Hello]
step: print
result: "hello trust"
status: completed
```

