# 4. Primitives

Trust contains standard primitives:

```trust id="j74gdo"
let count: Int = 10
let price: Float = 15.5
let active: Bool = true
let name: String = "Acme"
```

But Trust also introduces coordination primitives:

```trust id="fiyf9d"
let timeout: Duration = 5.minutes
let budget: Money = $20
let probability: Probability = 0.92
```

These primitives exist because autonomous systems operate in:

* time,
* economics,
* uncertainty.

Example:

```trust id="41v1i2"
workflow PaymentRetry {
  timeout 30.seconds
  budget <$2

  step charge_customer()
}
```

The compiler and runtime can reason about:

* timeouts,
* resource usage,
* execution costs.

