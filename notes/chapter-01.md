# Project Setup

## Inner Dev Loop

This is the loop that a developer goes through in each iteration locally. The faster this, the more iterations can be done.

### Faster Linking
I haven't set this up yet due to space constraints of XCode, but on MacOS, `zld` is the faster linker that should be setup.

### Cargo Watch

Something similar to nodemon for node, it reruns commands when files change, but much more ergonomic in my opinion.

Installation:
```bash
$> cargo install cargo-watch
```

Running It:
```bash
$> cargo watch -x check -x test -x run
```
This runs `cargo-check`, if they succeed, it runs the tests, and if they pass, it runs the software.

## CI

CI is done through Github actions in this repo, [look here](./.github/workflows).

CI Steps include
- **Testing**
- **Test Coverage Check** - `cargo tarpaulin`
- **Linting** - `cargo clippy`
- **Formatting**  - `cargo fmt`
- **Security Audit** - `cargo audit`

> NOTE: Most of these are done using cargo plugins.
