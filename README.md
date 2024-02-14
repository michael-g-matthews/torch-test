# torch-test
An example C++/Cuda application testing [libtorch](https://github.com/pytorch/pytorch) with the [Meson](https://mesonbuild.com/) build system. Based off of [this tutorial](https://pytorch.org/cppdocs/installing.html) that uses [CMake](https://cmake.org/).

## Installing Dependencies
### libtorch

Download the Cuda-enabled cxx11 ABI and install within `/opt`.


```shell
wget https://download.pytorch.org/libtorch/cu121/libtorch-cxx11-abi-shared-with-deps-2.1.2%2Bcu121.zip
sudo unzip libtorch-shared-with-deps-latest.zip -d /opt
```

> **Note**: The apt package `libtorch-dev` exists, but it is the CPU-only version of the library, so it does not meet our use-case.


## Build from Source

### CMake
```shell
mkdir build
cmake -DCMAKE_PREFIX_PATH=/opt/libtorch -B build -S . -G Ninja
cmake --build build --config Release
```

### Meson
```shell
meson setup build --native-file=native-clang.ini
meson compile -C build
```

## Run

```shell
build/example-app
```
