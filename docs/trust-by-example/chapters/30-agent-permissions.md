# 30. Agent Permissions

Permissions define what an agent may do.

Example:

```trust id="y2t4le"
agent ResearchBot {
  can_use [Browser]
}
```

Restricted action:

```trust id="q3v6pu"
action delete_database()
  requires AdminPermission
```

Permission violation:

```text id="t0k5nv"
coordination error:
agent ResearchBot lacks AdminPermission
```

Permissions allow safe multi-agent systems with isolation boundaries.

