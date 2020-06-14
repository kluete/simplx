# About

Simplx is a C++ development framework for building reliable cache-friendly distributed and concurrent multicore software.

Simplx was developed by **Tredzone SAS (\*)**, who provided software technology solutions and services dedicated to high-performance real-time processing. The technology enables low and predictable latency, scalability, and high throughput. Tredzone also offered support contracts and enterprise tools for monitoring, profiling, debugging, server clustering under commercial licenses.

Simplx is used at the Paris stock exchange by Euronext's market exchange platform, called "Optiq", and has been successfully deployed since November 2016.

Tredzone was founded in 2013 and operated in France, the UK and US.

(*) company ceased operations in June 2019


## Requirements

This code has been built and unit-tested on Linux with:

- Linux kernel 2.6+
- g++ versions 4.9.4, 5.5, 6.4, 7.3 and 8.3
- clang++ 3.9.1 with the libstdc++ runtime

It requires either C++ 11, 14 or 17 and the pthreads library. Support for Windows/VisualC++ will be announced soon.


## License

Simplx is open-sourced under the Apache 2.0 license, please see the [accompanying License](./LICENSE).  


## Getting Started

About a dozen tutorials are included here, please see the [Tutorials README](./tutorials/README.md).

To build all tutorials, open a terminal at the root of the repository and type:

```
mkdir build
cd build
cmake ..
make -j8
```


## Unit Tests

To build and run the unit tests, which depend on the Google Test submodule, open a terminal at the root of the repository and type:

```
git submodule update --init thirdparty/googletest
mkdir tbuild && cd tbuild
cmake -DBUILD_TEST=1 ..
make -j8
```

to then run the unit tests type:

```
make test
```


## Docker

There's a Bash that'll compile the tutorials and run the unit tests under all above-mentionned versions of gcc and clang under Docker:

```
./test/docker_test.sh
```

If a compilation or unit test failure occurs, the script will stop and report the error.

The 1st run takes a while to download the Docker images, as per usual with Docker.
 

## Documentation

To generate the documentation, open a terminal at the repository root and type

```
doxygen doc/Doxyfile
```
