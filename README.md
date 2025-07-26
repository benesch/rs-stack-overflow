# Rust stack overflow repro demo

Thread names have gone missing in stack overflow messages in Rust v1.89.

The likely culprit is rust-lang/rust#141232.

Reproduces on both Darwin and Linux.

## Beta (regression)

```
$ rustc +beta --version
rustc 1.89.0-beta.7 (4229c2e70 2025-07-25)

$ cargo +beta run
thread '<unknown>' has overflowed its stack
fatal runtime error: stack overflow, aborting
Aborted
```

```
$ rustc +stable --version
rustc 1.88.0 (6b00bc388 2025-06-23)

$ cargo +stable run
thread 'main' has overflowed its stack
fatal runtime error: stack overflow, aborting
Aborted
```
