# 25. Contracts

Contracts define behavioral interfaces between systems.

Example:

```trust id="u6m5eo"
contract PaymentProvider {
  fn charge(amount: Money)
  fn refund(payment: PaymentId)
}
```

Contracts specify:

* required actions,
* guarantees,
* failure semantics,
* permissions.

Implementation:

```trust id="p9n0fa"
provider Stripe implements PaymentProvider
```

Contracts allow workflows to remain deterministic even when external providers differ internally.

