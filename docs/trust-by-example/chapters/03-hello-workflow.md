# Hello Workflow

This chapter starts with the smallest useful Trust program: a workflow that
accepts a request, creates a durable record, and emits an event.

## Hello

```trust
workflow HelloWorkflow(name: Text) -> Greeting {
    let message = "Hello, " + name

    create greeting Greeting {
        message,
        created_at: now()
    }

    emit GreetingCreated(greeting.message)

    return greeting
}
```

## What Happens

The workflow performs four steps:

1. Bind a local value.
2. Create durable state.
3. Emit an event.
4. Return a typed result.

Unlike a normal function, a workflow has coordination semantics. The runtime can
record its execution, resume it after failure, and replay it deterministically
when all external actions are represented by recorded events.

## Source

See [hello_workflow.trust](../examples/hello_workflow.trust).

