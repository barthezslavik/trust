# 20. Packages

Packages distribute reusable Trust systems.

A package may contain:

* workflows,
* policies,
* agents,
* runtime integrations,
* contracts.

Example:

```text id="f7j5vo"
trust install browser-runtime
```

Package manifest:

```trust id="d2f7yo"
package browser-runtime {
  version "1.0.0"
  requires Trust >= 0.1
}
```

Packages may be:

* signed,
* verified,
* sandboxed.

Trust packages are intended to distribute coordination logic, not only libraries.

