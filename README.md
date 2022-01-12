# Setup Cargo Bin
 Easy and cached installation of Cargo binaries

# Example
 The [test action](.github/workflows/test-action.yml) for this repository is a good example of how to use this workflow, all it requires is this execution:

 ```yaml
 - uses: actions/setup-cargo-bin@v1
   with:
     bin-name: 'A crates.io binary crate, like "cargo-modules" or "mdbook"'
 ```

 The installation will be cached, so it won't be installated every time you run the workflow.
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