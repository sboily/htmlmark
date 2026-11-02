# Contributing

Before a pull request:

```sh
cargo fmt --check
cargo clippy --all-targets -- -D warnings
cargo test
```

A fix comes with a test that fails without it. An escaping or emphasis change
also runs the read-back property test further:

```sh
HTMLMARK_DOCUMENTS=50000 HTMLMARK_SEED=7 cargo test --release --test commonmark
```

and, with a nightly toolchain and `cargo install cargo-fuzz`, a few minutes of
each fuzz target:

```sh
cargo +nightly fuzz run read_back -- -dict=fuzz/html.dict -max_len=4096
cargo +nightly fuzz run convert -- -dict=fuzz/html.dict -max_len=4096
```

Library code never panics on input: the lints in `Cargo.toml` refuse
`unwrap`, `expect`, indexing and string slicing outside tests. Commit subjects
read `type(scope): summary`, at most 72 characters.
