`RUST_LOG=INFO wasm-pack test --chrome --headless -- --features some_feature`, output:

```
 INFO 2019-08-12T10:15:30Z: wasm_pack::command: Running test command...
 INFO 2019-08-12T10:15:30Z: wasm_pack::command::test: Checking rustc version...
 INFO 2019-08-12T10:15:30Z: wasm_pack::command::test: Rustc version is correct.
 INFO 2019-08-12T10:15:30Z: wasm_pack::command::test: Adding wasm-target...
[INFO]: Checking for the Wasm target...
 INFO 2019-08-12T10:15:30Z: wasm_pack::build::wasm_target: Looking for wasm32-unknown-unknown in "/home/alexlapa/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib"
 INFO 2019-08-12T10:15:30Z: wasm_pack::build::wasm_target: Found wasm32-unknown-unknown in "/home/alexlapa/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib"
 INFO 2019-08-12T10:15:30Z: wasm_pack::command::test: Adding wasm-target was successful.
 INFO 2019-08-12T10:15:30Z: wasm_pack::command::test: Compiling tests to wasm...
 INFO 2019-08-12T10:15:30Z: wasm_pack::child: Running "cargo" "build" "--tests" "--target" "wasm32-unknown-unknown"
   Compiling wasm-pack-698-reproduction v0.1.0 (/home/alexlapa/CLionProjects/wasm-pack-698-reproduction)
error[E0432]: unresolved import `wasm_pack_698_reproduction::foo`
 --> tests/integration_tests.rs:9:9
  |
9 |     use wasm_pack_698_reproduction::foo;
  |         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ no `foo` in the root

error: aborting due to previous error

For more information about this error, try `rustc --explain E0432`.
error: Could not compile `wasm-pack-698-reproduction`.

To learn more, run the command again with --verbose.
Error: Compilation of your program failed
Caused by: failed to execute `cargo build`: exited with exit code: 101
```