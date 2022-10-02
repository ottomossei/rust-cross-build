# rust-cross-builder
## Preparation
HOST PC (ubuntu, x86_64-unknown-linux-gnu)
```bash
# build
# Ex) docker build -f ./dockerfiles/HOST/Dockerfile -t myubuntu .
docker build -f ./dockerfiles/HOST/Dockerfile -t ${IMAGE_NAME_HOST} .

# start
# Ex) docker container run -v $(pwd):/mnt/ -it myubuntu
docker container run -v ${PWD}:/mnt/ -it ${IMAGE_NAME_HOST}
```

Target PC (alpine, x86_64-unknown-linux-musl)
```bash
# build
# Ex) docker build -f ./dockerfiles/TARGET/Dockerfile -t myalpine .
docker build -f ./dockerfiles/TARGET/Dockerfile -t ${IMAGE_NAME_TARGET} .

# start
# Ex) docker container run -v $(pwd):/mnt/ -it myalpine
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
# build
make build

# run
make run
```