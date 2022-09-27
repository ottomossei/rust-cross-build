# rust-cross-builder
## Preparation
HOST PC (ubuntu, x86_64-unknown-linux-gnu)
```bash
# build
docker build -f ./dockerfiles/HOST/Dockerfile -t ${IMAGE_NAME_HOST} .

# start
docker container run -v ${PWD}:/mnt/ -it ${IMAGE_NAME_HOST}
```

Target PC (alpine, x86_64-unknown-linux-musl)
```bash
# build
docker build -f ./dockerfiles/TARGET/Dockerfile -t ${IMAGE_NAME_TARGET} .

# start
docker container run -v ${PWD}:/mnt/ -it ${IMAGE_NAME_TARGET}
```

## setup cross-chain-tool on HOST PC
```bash
# target list
rustup target list

# install toolchain?
rustup target add x86_64-unknown-linux-musl

# show default target
rustup show

```

## build target on HOST
```bash
cargo build
```