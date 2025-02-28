# versatus-rust

This crate contains a work-in-progress for making it easy to develop smart contracts for the Versatus network in Rust. Other repos and packages exist for other languages. This crate and its documentation are in their very early stages and not yet ready for human consumption.

That said...

Build the sample with:

```
cargo build --release --example contract-split-evenly
```

We declared target to be set to `wasm32-wasi` by default in the `.cargo` crate; inside you'll find `config.toml` which you can copy if you'd like to do the same.
Otherwise it will be necessary to call `--target wasm32-wasi` at the end of of any build commands.

If you don't already have the `wasm32-wasi` Rust target installed, you can install it with `rustup`.

```
rustup target add wasm32-wasi
```

To run it, you can use any WASI-capable WASM runtime (such as wasmer 4.1) to test it with the sample JSON file provided:

```
wasmer target/wasm32-wasi/release/examples/contract-split-evenly.wasm \
    < examples/sample-contract-input.json
```

It should display a list of transactions on standard output.

