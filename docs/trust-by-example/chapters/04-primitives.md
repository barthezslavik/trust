# Primitives

Trust starts with a small set of primitive values. Domain meaning is usually
added with semantic types, but primitives are useful at the edges.

## Values

```trust
let name: Text = "Ada"
let active: Bool = true
let attempts: Int = 3
let score: Float = 0.98
let created_at: Instant = now()
let delay: Duration = 5.minutes
```

## Collections

```trust
let tags: List<Text> = ["trial", "crm"]
let counts: Map<Text, Int> = {
    "accepted": 10,
    "rejected": 2
}
```

## Prefer Meaningful Types

Primitive values are easy to pass to the wrong place. Trust encourages semantic
types for values that carry business or safety meaning.

```trust
semantic type CustomerId = Text
semantic type EmailAddress = Text
semantic type RetryCount = Int
```

