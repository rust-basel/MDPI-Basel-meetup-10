
## A small opioninated place for Rust development setup

Install rust https://www.rust-lang.org/learn/get-started
  
### Learn rust
https://www.rust-lang.org/learn

### Init an application
```bash
cargo init
```

### Run the application
```bash
cargo run
```

### Run the tests
```bash
cargo test
```

### Add a dependency
```bash
cargo add rand
```

### Update the lockfile
```bash
cargo update
```

### Lint the code
```bash
cargo fmt --all -- --check
cargo clippy
```

### Format the code
```bash
cargo fmt
```

### Fix the code?
```bash
cargo fix --allow-dirty --allow-staged
```

### Build the application
```bash
cargo build --release
```

## A simply docker file

```Dockerfile

# Build stage
FROM rust:1.85-slim as builder

# Create a new empty shell project
WORKDIR /usr/src/app
COPY . .

# Build your program for release
RUN cargo build --release

# Run stage
FROM debian:bookworm-slim

# Copy the build artifact from the build stage
COPY --from=builder /usr/src/app/target/release/your_app /usr/local/bin/

# Set the startup command
CMD ["your_app"]

```

### Some libraries

- [actix-web - server/ecosystem](https://crates.io/crates/actix)
- [rocket - server/ecosystem](https://crates.io/crates/rocket)
- [axum - server/ecosystem](https://crates.io/crates/axum)
- [maud - html generator](https://crates.io/crates/maud)
- [clap - cli parser](https://crates.io/crates/clap)
- [serde - serialization](https://crates.io/crates/serde)
- [reqwest - http client](https://crates.io/crates/reqwest)
- [include_directory - include files](https://crates.io/crates/include_directory)
- [rand](https://crates.io/crates/rand)
- [leptos - view/wasm](https://crates.io/crates/leptos)

### Some js and css that pair well with Rust

- [htmx](https://htmx.org/)
- [tailwindcss](https://tailwindcss.com/)
- [alpine.js](https://alpinejs.dev/)  
- [mvp.css](https://andybrewer.github.io/mvp/)
- [pico.css](https://picocss.com/)

### Some tools that work well with Rust

- [just runner - simple task runner/composer](https://github.com/casey/just)
- [cargo machetete - remove unused deps](https://github.com/bnjbvr/cargo-machete)