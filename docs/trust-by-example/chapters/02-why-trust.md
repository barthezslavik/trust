# Why Trust?

Coordination software often starts simple and becomes fragile as soon as it
crosses boundaries: a payment provider, a human review queue, a browser session,
an LLM call, a CRM update, a worker retry, or a distributed lock.

Trust exists to make those boundaries visible and checkable.

## The Problem

In many systems, critical rules live in different places:

- Access rules live in middleware.
- State rules live in application code.
- Retry rules live in job configuration.
- Audit rules live in database triggers.
- Human approval rules live in ticket workflows.
- LLM safety rules live in prompts.

That split makes the system hard to reason about. A local code change can break
a global coordination rule.

## The Trust Approach

Trust puts coordination into the language surface:

```trust
capability ChargeCustomer {
    provider: Stripe
    max_amount: Money<USD>
    valid_until: Instant
}

workflow CollectInvoice(invoice: Invoice)
    requires ChargeCustomer
{
    invariant invoice.total <= ChargeCustomer.max_amount

    charge invoice.customer for invoice.total
        using ChargeCustomer
        idempotency invoice.id
}
```

The program says which authority is required, how much money can move, when the
authority expires, and how duplicate execution is controlled.

## When Trust Is a Fit

Trust is designed for:

- Durable workflows.
- Multi-agent systems.
- Human-in-the-loop automation.
- Browser and tool runtimes.
- Event-sourced systems.
- Compliance-sensitive automation.
- Distributed coordination with replay requirements.

