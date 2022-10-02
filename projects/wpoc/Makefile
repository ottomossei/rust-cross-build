SHELL=/bin/bash

#####
# wpoc is proof of concept about wasmer compiled on debian linux to run alpine linux.
# We learn about these tips.
# ・cross compile for musl-libc
# ・dylib & cdylib
#####
all: build

build: build-wpoc build-capi
run: run-wpoc run-capi

build-wpoc:
	cargo build --manifest-path lib/cli/Cargo.toml --bin wpoc  --release 

build-capi:
	cargo build --manifest-path lib/c-api/Cargo.toml --release

run-wpoc:
	cargo run --manifest-path lib/cli/Cargo.toml

run-capi:
	cargo run --manifest-path lib/c-api/Cargo.toml