# Writing an OS in Rust

This repository follows the blog series "Writing an OS in Rust" by Philipp Oppermann.

The original blog series can be found [here](https://os.phil-opp.com/).

## Building

This project requires a nightly version of Rust because it uses some unstable features. At least nightly _2020-07-15_ is required for building. You might need to run `rustup update nightly --force` to update to the latest nightly even if some components such as `rustfmt` are missing it.

Before building you'll need to install [`bootimage`], and a couple of components through [`rustup`].

[`bootimage`]: https://github.com/rust-osdev/bootimage
[`rustup`]: https://rustup.rs/

To install the [`bootimage`] tool, run the following from any directory outside the project directory:

```
cargo install bootimage
```

To install the required components through [`rustup`], run the following inside the project directory:

```
rustup component add rust-src --toolchain nightly
rustup component add llvm-tools-preview
```

You can build the project by running:

```
cargo build
```

To create a bootable disk image from the compiled kernel, you need to install the [`bootimage`] tool:

```
cargo install bootimage
```

After installing, you can create the bootable disk image by running:

```
cargo bootimage
```

This creates a bootable disk image in the `target/x86_64-os_target/debug` directory.

## Running

You can run the disk image in [QEMU] through:

[QEMU]: https://www.qemu.org/

```
cargo run
```

## Testing

You can run the unit and integration tests through:

```
cargo test
```
