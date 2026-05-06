# 19. Modules

Modules organize Trust systems into coordination domains.

```trust id="u7v4r0"
module crm
module browser
module outreach
```

Modules may contain:

* workflows,
* agents,
* contracts,
* policies,
* runtime utilities.

Example:

```trust id="8f9v2n"
module outreach {
  workflow SendCampaign
  action send_email
}
```

Modules create execution boundaries and visibility scopes.

Imports:

```trust id="m4n8qs"
use crm.Lead
use outreach.SendCampaign
```

Trust modules are designed around operational domains rather than low-level code organization.

