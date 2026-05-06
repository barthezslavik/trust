# 5. Semantic Types

Traditional languages treat most data as raw primitives:

```rust id="9q7vbo"
String
i32
bool
```

Trust encourages semantic meaning.

```trust id="9ix0fa"
type Email
type VerifiedUrl
type LeadScore = 0..100
type BudgetLimit = Money where value > 0
```

Semantic types allow the compiler to enforce coordination correctness.

Example:

```trust id="zmxh8j"
fn send_email(to: Email)
```

This function cannot receive:

* random strings,
* malformed addresses,
* unverified input.

More advanced example:

```trust id="6y6y4u"
type ApprovedLead where {
  score > 80
  consent == true
  email.is_verified()
}
```

Now workflows can require proof that a lead satisfies business rules before execution continues.

Semantic types are foundational to Trust because autonomous systems cannot safely operate on untrusted data.

