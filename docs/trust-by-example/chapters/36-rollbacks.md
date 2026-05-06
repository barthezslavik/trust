# 36. Rollbacks

Rollbacks reverse workflow effects after failure.

Example:

```trust id="o3u7ki"
rollback {
  remove_crm_record()
  refund_payment()
}
```

Rollback example:

```trust id="a1t5cq"
workflow Checkout {
  step charge_customer()
  step reserve_inventory()

  rollback {
    refund_payment()
    release_inventory()
  }
}
```

Rollbacks are causally connected to original actions.

