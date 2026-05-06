# 21. Trust Toolchain

The Trust toolchain manages:

* compilation,
* execution,
* replay,
* auditing,
* coordination checking.

Basic commands:

```text id="k7g9vh"
trust build
trust run
trust check
trust replay
trust audit
```

Example:

```text id="x8s3fk"
trust check
```

Output:

```text id="v0r2mf"
checking workflows...
checking transitions...
checking capabilities...
checking temporal validity...

0 coordination errors found
```

The toolchain understands:

* workflows,
* causality,
* execution history,
* distributed state.

Unlike traditional compilers, Trust validates operational correctness.

