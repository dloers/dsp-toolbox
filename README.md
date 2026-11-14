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

### Build as shared library

```bash
cmake -S . -B build \
    -BUILD_SHARED_LIBS=ON
```

### Build Examples

```bash
cmake -S . -B build \
    -DDSP_TOOLBOX_BUILD_EXAMPLES=ON
```
