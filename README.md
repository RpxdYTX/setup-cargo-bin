# Setup Cargo Bin
 Easy and cached installation of Cargo binaries

# Example
 The [test action](.github/workflows/test-action.yml) for this repository is a good example of how to use this workflow, all it requires is this execution:

 ## Quick Note:
  The test action installs [`cross`](https://crates.io/crates/cross) which is licensed under the MIT License or Apache 2.0 License, `cross` is only used as a
  test in that workflow. The same applies for the upcoming example where [`cargo-modules`](https://crates.io/crates/cargo-modules) licensed under the MPL license
  is used, all of their rights reserved.

 Now back to the example:

 ```yaml
 - uses: actions/setup-cargo-bin@v1
   with:
     bin-name: 'A crates.io binary crate, like "cargo-modules" or "mdbook"'
 ```

 The first time you run it, the installation will be cached, so it won't be installated every time
 you run the workflow.
 Using the `args` input, you can pass arguments to Cargo during the installation, such as `--force`:

 ```yaml
 - uses: actions/setup-cargo-bin@v1
   with:
     bin-name: 'cargo-modules'
     args:
       - --force
 ```

# Note
 This action only runs `cargo install` for the specified binary and caches it, it won't runs the binary.
