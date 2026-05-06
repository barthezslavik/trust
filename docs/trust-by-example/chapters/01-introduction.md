# Introduction

Trust is a language for systems where the hard part is not only computation, but
coordination: who may act, when an action is valid, what state transition is
allowed, how failures are compensated, and how execution can be audited or
replayed later.

Most general-purpose languages can build these systems, but they often hide the
coordination model inside framework code, queues, databases, permissions tables,
and retry policies. Trust makes those coordination rules part of the program.

## A Small Example

```trust
workflow OnboardCustomer(input: SignupRequest) -> CustomerAccount {
    let email = verify input.email as VerifiedEmail

    reserve account_id from Accounts
        idempotency input.request_id

    create account CustomerAccount {
        id: account_id,
        email,
        state: PendingReview
    }

    emit CustomerOnboarded(account.id)

    return account
}
```

This example is intentionally compact. Later chapters unpack the pieces:
semantic types, ownership, capabilities, states, events, idempotency, audit
logs, and replay.

## What Trust Optimizes For

- Explicit authority: actions require capabilities.
- Explicit time: leases, deadlines, and temporal validity are typed concepts.
- Explicit state: workflows move through declared states and transitions.
- Explicit recovery: retries, rollbacks, and compensation are part of the model.
- Explicit evidence: logs and execution graphs are runtime artifacts, not
  afterthoughts.

