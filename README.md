# Scala compiler plugin example for Bazel

## Getting Started

Using bazel 0.27.1, run below to demonstrate the issue

```bash
bazel build //example-for-plugin/src:src
```

If working properly, the compiler plugin would raise below error during build

```bash
definitely division by zero
```
