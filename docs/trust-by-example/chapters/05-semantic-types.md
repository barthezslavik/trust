# Semantic Types

Semantic types give primitive values a domain meaning. They prevent accidental
mixing of values that have the same representation but different intent.

## Define a Semantic Type

```trust
semantic type EmailAddress = Text
semantic type VerifiedEmail = EmailAddress
semantic type CustomerId = Text
```

`EmailAddress` and `CustomerId` may both be represented as text, but they are not
interchangeable.

## Convert With Evidence

```trust
function verify_email(email: EmailAddress) -> VerifiedEmail
    ensures valid(email)
{
    external EmailVerifier.check(email)
    return email as VerifiedEmail
}
```

The conversion from `EmailAddress` to `VerifiedEmail` is meaningful because the
function records the evidence required by its contract.

## Use Semantic Types in Workflows

```trust
workflow InviteCustomer(email: EmailAddress) -> Invitation {
    let verified = verify_email(email)

    create invitation Invitation {
        email: verified,
        state: PendingAcceptance
    }

    emit InvitationSent(invitation.email)

    return invitation
}
```

