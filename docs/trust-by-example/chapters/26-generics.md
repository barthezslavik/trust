# 26. Generics

Generics allow reusable coordination abstractions.

Example:

```trust id="a2m3xy"
workflow Retry<T>
```

Generic workflow:

```trust id="v7s4ja"
workflow Retry<T> {
  step execute(T)
}
```

Generic contracts:

```trust id="g3j2rk"
contract Repository<T> {
  fn save(item: T)
}
```

Trust generics focus heavily on:

* reusable workflows,
* reusable policies,
* reusable orchestration patterns.

