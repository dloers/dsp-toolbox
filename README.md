# DSP-Toolbox - Digital Signal Processing (DSP) Library

A C library for working with digital signals, offering tools for filtering, transformation, signal analysis and generation.

## Quick Start

### Prerequisites

- CMake 3.14 (Meta-build tool)

### Installation

1. Clone the repository.

```bash
git clone https://github.com/dloers/dsp-toolbox.git 
```

2. Initialize the build system.

```bash
cmake -S . -B build
```

### Usage

Building the project

```bash
cmake --build build
```

## Build Configuration

### CMake Options

| **Option** | **Default** | **Description** |
|---|---|---|
| ```BUILD_SHARED_LIBS``` | ```OFF``` | Build the library as a shared library (```ON```) or a static library (```OFF```). |
| ```DSP_TOOLBOX_BUILD_EXAMPLES``` | ```OFF``` | Build the included examples. |
| ```DSP_TOOLBOX_BUILD_TESTS``` | ```OFF``` | Build the libraries' unit tests. |

### Build as shared library

1. Configure the build system to compile the code as a shared libray by running:

```bash
cmake -S . -B build \
    -DBUILD_SHARED_LIBS=ON
```

### Build Examples

1. To enable the compilation of the examples run:

```bash
cmake -S . -B build \
    -DDSP_TOOLBOX_BUILD_EXAMPLES=ON
```

### Build Tests

1. Enable unit testing by running:

```bash
cmake -S . -B build \
    -DDSP_TOOLBOX_BUILD_TESTS=ON
```

2. After (re)initializing the build system, run the tests with:

```bash
ctest --test-dir build --output-on-failure
```
