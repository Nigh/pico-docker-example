# pico docker example
a example of compiling raspberry pi pico with docker.

## Pull the docker

```bash
docker pull xianii/pico-sdk:latest
```
Before you start compiling, you should get your docker image ready.

## Compile pico-example

The commands below shows how to compile the `pico-examples` with the docker.

```bash
git clone --depth=1 https://github.com/raspberrypi/pico-examples
cd pico-examples
docker run --rm -v ${PWD}:/pico-src xianii/pico-sdk:latest /bin/bash -c "cd pico-src && cmake . -G Ninja -Bbuild -S. && ninja -C build"
```

## Compile this blink example

Run the command below at the same folder with this README.

```bash
docker run --rm -v ${PWD}:/pico-src xianii/pico-sdk:latest /bin/bash -c "cd pico-src && cmake . -G Ninja -Bbuild -S. && ninja -C build"
```

The `uf2` firmware will then appear in the path `. /build/blink_simple/blink_simple.uf2`

> [!TIP]  
> The `${PWD}` is the absolute path of current path since the docker mount path do not accept relative path.  
> If the `${PWD}` do not work at your shell environment, just replace it with the correct absolute path.
