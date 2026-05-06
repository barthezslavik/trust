# 6. Custom Types

Custom types allow developers to model real-world coordination objects.

```trust id="c7w6wy"
type Lead {
  company: String
  website: VerifiedUrl
  email: Email
  score: LeadScore
}
```

Unlike traditional DTO-style objects, Trust types are designed to participate in:

* workflows,
* policies,
* permissions,
* invariants,
* causality graphs.

Types may contain validation rules:

```trust id="08t4r4"
type Payment {
  amount: Money where value > 0
  currency: Currency
}
```

Or execution guarantees:

```trust id="bx56h8"
type VerifiedCustomer where {
  kyc.completed == true
  fraud_score < 0.2
}
```

This allows invalid business states to become unrepresentable.

