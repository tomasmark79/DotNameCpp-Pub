<img src="assets/DotNameCppLogo.svg" width="100%" onerror="this.style.display='none'">

# DotNameCpp - Advanced C++ Development Template

A comprehensive, production-ready C++ development template designed for rapid project initialization with modern tooling, cross-platform support, and automated workflows. This template provides everything needed to start developing native and cross-platform C++ applications efficiently and cleanly.

<span id="linux-badge"><a href="https://github.com/tomasmark79/DotNameCpp/actions/workflows/linux.yml"><img src="https://github.com/tomasmark79/DotNameCpp/actions/workflows/linux.yml/badge.svg?branch=main" alt="" onerror="document.getElementById('linux-badge').remove()" style="border:0;"></a></span> <span id="macos-badge"><a href="https://github.com/tomasmark79/DotNameCpp/actions/workflows/macos.yml"><img src="https://github.com/tomasmark79/DotNameCpp/actions/workflows/macos.yml/badge.svg?branch=main" alt="" onerror="document.getElementById('macos-badge').remove()" style="border:0;"></a></span> <span id="windows-badge"><a href="https://github.com/tomasmark79/DotNameCpp/actions/workflows/windows.yml"><img src="https://github.com/tomasmark79/DotNameCpp/actions/workflows/windows.yml/badge.svg?branch=main" alt="" onerror="document.getElementById('windows-badge').remove()" style="border:0;"></a></span>

---

> **Expert Assessment**: *"This C++ template achieves production-grade quality with exceptional CMake organization, comprehensive tooling integration, and modern development practices. The automated workflows, cross-platform support, and developer experience represent industry best practices."* - GitHub Copilot (2025)

## 🛠️ Implementation Details

### ✅ Completed Features (2023-2025)
- **Multi-platform CI/CD**: Full GitHub Actions integration for Linux, macOS, Windows
- **Code Coverage**: Comprehensive gcovr integration with HTML/XML reports
- **WebAssembly Support**: Complete Emscripten integration with live demos
- **Development Tools**: clang-tidy, clang-format, cmake-format automation
- **VSCode Integration**: Extensive keyboard shortcuts and task automation
- **Cross-Toolchain Management**: Seamless integration with popular C++ toolchains
- **Container Support**: Docker integration planned but not yet implemented

### 🚧 Current Limitations
- **Coverage Analysis**: Only available for native builds (`default` architecture)
- **Help System**: SolutionController.py help documentation planned but not yet started

### 🎯 Upcoming Features (2025+)
- Enhanced container development workflows
- Performance profiling integration
- Creation of Conan Package from the project

---

## 📚 Table of Contents

- [🚀 Overview](#-overview)
- [✨ Key Features](#-key-features)
- [⚡ Quick Start](#-quick-start)
- [🛠️ Prerequisites & Dependencies](#️-prerequisites--dependencies)
- [🏗️ Project Structure](#️-project-structure)
- [🔧 Build System](#-build-system)
- [📦 Package Management](#-package-management)
- [🧰 Development Tools](#-development-tools)
- [💻 IDE Integration](#-ide-integration)
- [🌍 Cross-Platform Development](#-cross-platform-development)
- [🌐 WebAssembly & Emscripten](#-webassembly--emscripten)
- [🧪 Testing Framework](#-testing-framework)
- [📚 Library Development](#-library-development)
- [🔄 CI/CD Pipeline](#-cicd-pipeline)
- [🛠️ Maintenance & Utilities](#️-maintenance--utilities)
- [📖 Documentation](#-documentation)
- [📄 License](#-license)

---

## 🚀 Overview

**DotNameCpp** is more than just a project template—it's a complete development ecosystem that streamlines C++ development from conception to deployment. Designed with modern C++ best practices, it provides a robust foundation for both library and standalone application development.

This template has been crafted to eliminate the initial setup overhead that typically accompanies C++ projects, allowing developers to focus on writing code rather than configuring build systems and toolchains.

### 🎯 Design Philosophy

- **Zero-Configuration Start**: Get productive immediately with sensible defaults
- **Scalability**: Grows from simple prototypes to complex multi-platform applications
- **Developer Experience**: Prioritizes ease of use without sacrificing power
- **Modern Standards**: Embraces C++20/23 features and contemporary tooling
- **Production Ready**: Includes all necessary components for professional development

---

## ✨ Key Features

### 🏗️ **Advanced Build System**
- **CMake 3.31+** with modern preset system
- **Conan 2.0** integration for dependency management
- **Ninja** build system for fast compilation
- **ccache** support for accelerated rebuilds
- **Cross-compilation** ready with toolchain support

### 🌐 **Multi-Platform Support**
- **Native Development**: Linux, macOS, Windows
- **WebAssembly**: Emscripten integration for web deployment
- **Cross-Compilation**: ARM, x86, x64 architectures
- **Container Support**: Docker and GitHub Codespaces ready

### 🧰 **Development Tools Integration**
- **Static Analysis**: clang-tidy with comprehensive rule sets
- **Code Formatting**: clang-format and cmake-format
- **Documentation**: Doxygen with automated generation
- **Testing**: Google Test framework integration
- **Debugging**: GDB/LLDB support with VSCode integration
- **Debugging**: CMake files support with VSCode integration

### 📦 **Project Flexibility**
- **Dual Structure**: Library and standalone application support
- **Modular Architecture**: Reusable components and utilities
- **Asset Management**: Integrated resource handling system
- **Licensing**: Built-in license collection and management

### 🚀 **Automation & CI/CD**
- **GitHub Actions**: Multi-platform CI/CD pipelines
- **Automated Testing**: Unit tests, integration tests, and benchmarks
- **Release Management**: Automated packaging and distribution
- **Quality Gates**: Static analysis and code coverage integration

---

## ⚡ Quick Start

### 🛠️ Clone the Repository

```bash
git clone git@github.com:tomasmark79/DotNameCpp.git
```

### 🛠️ Clone the Repository with removal of .git with simple command
add this function to your `.bashrc` or `.zshrc`:

```bash
clonedotname() {
    local PN="${1:-AppName}"
    git clone git@github.com:tomasmark79/DotNameCpp.git "$PN" && rm -rf "$PN/.git" && cd "$PN"
    python SolutionRenamer.py DotNameLib "$PN"Lib DotNameStandalone "$PN"Standalone
}
```

Then simply use:
```bash
clonedotname # Clone with default name "AppName"
clonedotname MyCustomAppName # Clone with custom name
```

### 🏗️ Quick Build

```bash
# Use the Python controller for advanced options - callable from VSCode tasks
python SolutionController.py standalone "🗡️ Conan install" default Debug
python SolutionController.py standalone "🔧 CMake configure" default Debug
python SolutionController.py standalone "🔨 Build" default Debug
```

### ☁️ GitHub Codespaces

```bash
pip install conan
conan profile detect
# Use the Python controller for advanced options - callable from VSCode tasks
python SolutionController.py standalone "🗡️ Conan install" default Debug
python SolutionController.py standalone "🔧 CMake configure" default Debug
python SolutionController.py standalone "🔨 Build" default Debug
```

Click the **Code** button on GitHub → **Codespaces** → **Create codespace** for instant cloud development environment.

### 🚀 One-Command Development

```bash
# Zero to Hero: Complete setup, build, test, and package
python SolutionController.py both "🦸 Zero to Hero" default Debug
```

---

## 🛠️ Prerequisites & Dependencies

### 🔧 Essential Tools

| Tool | Minimum Version | Purpose | Installation |
|------|----------------|---------|--------------|
| **Git** | 2.25+ | Version control | [Download](https://git-scm.com/downloads) |
| **CMake** | 3.31+ | Build system | [Download](https://cmake.org/download/) |
| **Conan** | 2.0+ | Package manager | `pip install conan` |
| **Python** | 3.8+ | Automation scripts | [Download](https://python.org) |
| **Ninja** | 1.10+ | Build tool | [Download](https://ninja-build.org/) |

### 🛡️ Recommended Tools

| Tool | Purpose | Installation |
|------|---------|--------------|
| **ccache** | Compilation cache | [Download](https://ccache.dev/download.html) |
| **clang-tidy** | Static analysis | Part of LLVM |
| **clang-format** | Code formatting | Part of LLVM |
| **cmake-format** | CMake formatting | `pip install cmake-format` |
| **Doxygen** | Documentation | [Download](https://www.doxygen.nl/download.html) |
| **gcovr** | Code coverage | `pip install gcovr` |

### 💻 Supported Compilers

| Platform | Compilers | Versions |
|----------|-----------|----------|
| **Linux** | GCC, Clang | GCC 11+, Clang 14+ |
| **macOS** | Clang, GCC | Xcode 14+, GCC 11+ |
| **Windows** | MSVC, Clang, GCC | VS 2022, Clang 14+, MinGW 11+ |
| **Emscripten** | emcc | 3.1.0+ |

---

## 🏗️ Project Structure

```
📁 DotNameCpp/
├── 📁 .github/                     # GitHub configuration files
├── 📁 .vscode/                     # Visual Studio Code configuration
├── 📁 assets/                      # Project resources
│   ├── customstrings.json          # Localization strings
│   ├── DotNameCppLogo.svg          # Project logo
│   └── ems-mini.html               # Emscripten template
├── 📁 build/                       # Build outputs (auto-generated)
│   ├── 📁 installation/            # Installation artifacts
│   ├── 📁 standalone/              # Standalone builds
│   └── 📁 tarballs/                # Distribution packages
├── 📁 cmake/                       # CMake modules and utilities
│   ├── project-common.cmake        # Common project settings
│   ├── project-library.cmake       # Library-specific configuration
│   ├── project-standalone.cmake    # Standalone app configuration
│   ├── tmplt-*.cmake               # Feature modules (sanitizers, hardening, etc.)
│   └── 📁 modules/                 # Custom CMake modules
├── 📁 conan_tools/                 # Conan integration utilities
├── 📁 doc/                         # Documentation (auto-generated)
├── 📁 include/DotNameLib/          # Public library headers
├── 📁 src/                         # Library source code
│   ├── DotNameLib.cpp              # Main library implementation
│   ├── 📁 Assets/                  # Asset management utilities
│   ├── 📁 Logger/                  # Logging functionality
│   └── 📁 Utils/                   # Utility classes
├── 📁 standalone/                  # Standalone application
│   ├── 📁 src/                     # Application source
│   └── 📁 tests/                   # Application tests
├── 📄 CMakeLists.txt               # Root CMake configuration
├── 📄 CMakeUserPresets.json        # CMake presets for different configurations
├── 📄 conanfile.py                 # Conan dependency specification
├── 📄 SolutionController.py        # Main Template automation script
├── 📄 SolutionRenamer.py           # Template renaming utility
└── 📄 SolutionUpgrader.py          # Template update utility
```

### 📂 Directory Purposes

- **`assets/`**: Static resources, configurations, and branding materials
- **`cmake/`**: Modular CMake configuration with reusable templates
- **`include/`**: Public API headers for library consumers
- **`src/`**: Library implementation with organized subsystems
- **`standalone/`**: Example application demonstrating library usage
- **`conan_tools/`**: Custom Conan integration and utility functions

---

## 🔧 Build System

### 🎛️ CMake Presets System

The project uses CMake presets for consistent, reproducible builds across different environments:

```bash
# List available presets
cmake --list-presets

# Configure with a preset
cmake --preset debug-linux-x86_64-gcc-15

# Build with a preset
cmake --build --preset debug-linux-x86_64-gcc-15
```

### 📋 Available Build Presets

Depends on your toolchain configuration. Every new build configuration should be added to the `CMakeUserPresets.json` file.

### 🔧 Build Options

Configure your build with these CMake options:

```cmake
# Core options
option(BUILD_LIBRARY "Build the DotNameLib library" ON)
option(BUILD_STANDALONE "Build the standalone application" ON)
option(BUILD_TESTS "Build unit tests" OFF)
option(BUILD_DOCS "Generate documentation" OFF)

# Feature options
option(ENABLE_HARDENING "Enable security hardening" OFF)
option(ENABLE_SANITIZERS "Enable runtime sanitizers" OFF)
option(ENABLE_IPO "Enable interprocedural optimization" OFF)
option(ENABLE_CCACHE "Use ccache for compilation" ON)
option(ENABLE_COVERAGE "Enable code coverage analysis" OFF)

# Platform-specific options
option(EMSCRIPTEN_BUILD "Build for Emscripten/WebAssembly" OFF)
```

> **⚠️ Important Coverage Note**: Code coverage analysis is **exclusively supported for native builds** using the `default` architecture. Cross-compilation targets (Emscripten, MinGW, ARM, etc.) cannot execute tests locally, therefore coverage data collection is not possible for these platforms. Always use native builds when coverage analysis is required.

### 🚀 Advanced Build Commands

```bash
# Complete workflow: clean → configure → build → test → package
python SolutionController.py both "🦸 Zero to Hero" default Debug

# Quick rebuild default Debug
python SolutionController.py both "🔨 Build" default Debug

# Clean build for default Debug
python SolutionController.py both "🧹 Clean selected folder" default Debug

# Build with code coverage enabled
cmake --preset debug-linux-x86_64-gcc-15 -DENABLE_COVERAGE=ON
cmake --build --preset debug-linux-x86_64-gcc-15
ctest --preset debug-linux-x86_64-gcc-15
make coverage

# Coverage workflow with SolutionController
python SolutionController.py standalone "📊 Configure with Coverage" default Debug
python SolutionController.py standalone "🔨 Build" default Debug
python SolutionController.py standalone "🧪 Run CTest" default Debug
python SolutionController.py standalone "📊 Coverage HTML Report" default Debug

# Cross-compilation example
python SolutionController.py standalone "🔨 Build" x86_64_linux-clang20 Release 
```

---

## 📦 Package Management

### 🔗 Conan 2.0 Integration

This template uses Conan 2.0 for modern, efficient dependency management:

```python
# conanfile.py excerpt
def requirements(self):
    # Core dependencies
    self.requires("fmt/10.1.1")
```

### 📋 Dependency Management Commands

```bash
# Install dependencies
conan install . --build=missing

# Create dependency graph
conan graph info . --format=html > dependencies.html

# Update dependencies
conan install . --update

# Create lockfile for reproducible builds
conan lock create .
```

### 🔄 Custom Conan Profile

Create optimized profiles for different scenarios:

```ini
# profiles/development
[settings]
os=Linux
arch=x86_64
compiler=gcc
compiler.version=13
compiler.libcxx=libstdc++11
build_type=Debug

[options]
*:shared=False
*:fPIC=True

[buildenv]
CC=gcc-13
CXX=g++-13
```

---

## 🧰 Development Tools

### 🔍 Static Analysis with clang-tidy

> For clang-tidy linting must exist build artifacts due to the nature of the analysis.

Comprehensive static analysis is integrated into the build system:

```bash
# Run static analysis
python SolutionController.py both "🔍 clang-tidy linting" default Debug

# Custom clang-tidy configuration
python SolutionController.py standalone "🔍 clang-tidy linting" default Debug
```

**Configuration in `.clang-tidy`**:
```yaml
Checks: >
  clang-diagnostic-*,
  clang-analyzer-*,
  cppcoreguidelines-*,
  modernize-*,
  performance-*,
  readability-*,
  bugprone-*,
  cert-*,
  misc-*
WarningsAsErrors: ''
CheckOptions:
  - key: readability-identifier-naming.VariableCase
    value: camelCase
  - key: readability-identifier-naming.FunctionCase
    value: camelCase
  - key: readability-identifier-naming.ClassCase
    value: PascalCase
```

### 🎨 Code Formatting

Consistent code style across the project:

```bash
# Format all C++ code
python SolutionController.py both "📐 clang-format" noNeedArch

# Format CMake files
python SolutionController.py both "📏 cmake-format" noNeedArch
```

---

## 💻 IDE Integration

### 🧠 Visual Studio Code Setup

This template provides deep VSCode integration with optimized settings and tasks.

#### ⌨️ Keyboard Shortcuts

| Shortcut | Action | Description |
|----------|--------|-------------|
| **F5** | Quick Debug | Start debugging standalone application |
| **F7** | Quick Build | Build standalone application |
| **Shift+F7** | Build Menu | Show comprehensive build options |
| **Ctrl+F7** | Other Tasks | Show utility and maintenance tasks |
| **Ctrl+Alt+F** | Format Code | Run clang-format on current file |
| **Ctrl+Alt+L** | Lint Code | Run clang-tidy analysis |
| **Ctrl+Alt+M** | Format CMake | Run cmake-format on CMake files |
| **Ctrl+Alt+P** | Build All Presets | Build all CMake presets |
| **Ctrl+Alt+R** | Run Standalone | Execute standalone binary |
| **Ctrl+Alt+E** | Launch Emscripten | Build and serve Emscripten version |
| **Ctrl+Alt+Shift+C** | Configure with Coverage | Configure build with coverage enabled |
| **Ctrl+Alt+Shift+H** | Coverage HTML Report | Generate and open HTML coverage report |
| **Ctrl+Alt+Shift+F** | Coverage Full Report | Generate both HTML and XML coverage reports |
| **Ctrl+Alt+Shift+T** | Coverage Tasks | Show coverage task menu |
| **Ctrl+Alt+Shift+O** | Coverage Tasks (Other) | Quick access to coverage tasks (native build only) |

#### 📋 VSCode Tasks

**🔨 Building Tasks (Shift+F7)**:
- **🚀 Zero to Build**: Complete clean build workflow
- **🦸 Zero to Hero**: Full development cycle with testing and packaging
- **🧹 Clean Build**: Remove build artifacts and rebuild
- **🗡️ Conan Install**: Install and update dependencies
- **🔧 CMake Configure**: Configure build system
- **📊 CMake configure with Coverage**: Configure build with code coverage enabled
- **🪲 CMake Configure with CMake-debugger**: Configure with CMake debugger
- **🔨 Build**: Compile the project
- **🧪 Run Tests**: Execute test suite
- **📜 Gather dependency licenses**: Gather dependency licenses
- **📌 Install built components**: Install built components
- **🗜️ Create Tarballs for distribution**: Package for distribution
- **🛸 Run CPack**: Create installation packages

**🛠️ Other Tasks (Ctrl+F7)**:
- **📖 Generate Documentation**: Create Doxygen documentation
- **📐 Format Code**: Apply code formatting
- **📏 Format CMake**: Format CMake files
- **⚔️ Create Conan Recipe**: Generate Conan package
- **📊 Dependency Graph**: Visualize project dependencies
- **🔍 Security Scan**: Run security analysis
- **🧪 Benchmark**: Run performance tests

**🔬 Coverage Tasks from Other Menu**:
- **📊 Coverage HTML Report**: Quick HTML report (native build only)
- **📊 Coverage XML Report**: Quick XML report (native build only)
- **📊 Coverage Summary**: Quick summary display (native build only)
- **📊 Coverage Full Report**: Quick full report (native build only)
- **📊 Coverage Reset**: Quick coverage reset (native build only)

#### 🎯 IntelliSense Configuration

Optimized C++ IntelliSense settings in `.vscode/c_cpp_properties.json`:

```json
{
    "configurations": [
        {
            "name": "Linux",
            "includePath": [
                "${workspaceFolder}/**",
                "/home/tomas/.cache/CPM/cxxopts/**",
                "/home/tomas/.cache/CPM/fmt*/**",
                "/home/tomas/.conan2/p/b/imgui*/**",
                "/home/tomas/.conan2/p/glm*/**",
                "/home/tomas/.conan2/p/nlohm*/**"
            ],
            "defines": [],
            "compilerPath": "${default}",
            "cStandard": "c11",
            "cppStandard": "c++17",
            "intelliSenseMode": "${default}",
            "recursiveIncludes": {
                "reduce": "always",
                "priority": "beforeSystemIncludes",
                "order": "breadthFirst"
            }
        }
    ],
    "version": 4
}
```

---

## 🌍 Cross-Platform Development

### 🖥️ Platform Support Matrix

| Feature | Linux | macOS | Windows | WebAssembly |
|---------|-------|-------|---------|-------------|
| **Native Build** | ✅ | ✅ | ✅ | N/A |
| **Cross-Compilation** | ✅ | ✅ | ✅ | ✅ |
| **Package Management** | ✅ | ✅ | ✅ | ✅ |
| **IDE Integration** | ✅ | ✅ | ✅ | ✅ |
| **CI/CD** | ✅ | ✅ | ✅ | ✅ |
| **Container Support** | ✅ | ✅ | ✅ | ✅ |

### 🔧 Cross-Compilation Setup

```bash
# ARM64 Linux from x86_64
conan install . -pr:h=profiles/arm64-linux -pr:b=default

# Windows from Linux
conan install . -pr:h=profiles/windows-x64 -pr:b=default

# Configure cross-compilation
cmake --preset cross-arm64-release
```

### 🐳 Container Development

**Status**: 🚧 **Planned for implementation**

```dockerfile
# Dockerfile.dev (planned)
FROM ubuntu:24.04

RUN apt-get update && apt-get install -y \
    build-essential \
    cmake \
    ninja-build \
    python3-pip \
    git \
    ccache \
    clang-tidy \
    clang-format

RUN pip3 install conan cmake-format gcovr
RUN conan profile detect

WORKDIR /workspace
COPY . .
RUN conan install . --build=missing
```

---

## 🌐 WebAssembly & Emscripten

### 🚀 Emscripten Integration

This template provides seamless WebAssembly development with Emscripten:

```bash
# Build for web deployment
python SolutionController.py both "🚀 Launch Emscripten Server" noNeedArch

# Quick Emscripten build
cmake --preset debug-emscripten-wasm-clang-20
cmake --build --preset debug-emscripten-wasm-clang-20
```

### 🎮 Web Application Features

- **Asset Preloading**: Automatic asset packaging for web deployment
- **Modern Web Standards**: ES6+ JavaScript integration
- **Responsive Design**: Mobile-friendly web interface
- **Performance Optimization**: WebAssembly-optimized builds

### 🌐 Live Demo

Experience the template in action:
- **Debug Version**: [DotNameStandalone.html (Debug)](https://digitalspace.name/dotnamecpp/preview/debug/DotNameStandalone.html)
- **Release Version**: [DotNameStandalone.html (Release)](https://digitalspace.name/dotnamecpp/preview/release/DotNameStandalone.html)

Experience with more complex scenarios: **GPU required**
- **Debug Version**: [DotNameStandalone.html (Debug)](https://digitalspace.name/dotnamecpp/i2/singularity/debug/index2.html)
- **Release Version**: [DotNameStandalone.html (Release)](https://digitalspace.name/dotnamecpp/i2/singularity/release/index2.html)

### 📱 Emscripten Configuration

```cmake
# cmake/tmplt-emscripten.cmake excerpt
if(EMSCRIPTEN)
    set_target_properties(${target} PROPERTIES
        SUFFIX ".html"
        LINK_FLAGS "
            --preload-file ${CMAKE_SOURCE_DIR}/assets@assets
            -s USE_SDL=2
            -s ALLOW_MEMORY_GROWTH=1
            -s EXPORTED_FUNCTIONS=['_main']
            -s EXPORTED_RUNTIME_METHODS=['ccall']
        "
    )
endif()
```

### 🎯 Web Deployment

```bash
# Serve locally for development
python -m http.server 8000 -d build/emscripten/debug

# Production deployment (planned)
# python SolutionController.py emscripten "🚀 Deploy Web" noNeedArch

# Current: Manual deployment to web server
# Copy build/emscripten/release/* to your web hosting service
```

---

## 🧪 Testing Framework

### 🔬 Google Test Integration

Comprehensive testing framework with Google Test:

```cpp
// Example test in standalone/tests/
#include <gtest/gtest.h>
#include "DotNameLib/DotNameLib.hpp"

class DotNameLibTest : public ::testing::Test {
protected:
    void SetUp() override {
        // Test setup
    }
};

TEST_F(DotNameLibTest, BasicFunctionality) {
    EXPECT_TRUE(DotNameLib::isInitialized());
    EXPECT_EQ(DotNameLib::getVersion(), "1.0.0");
}
```

### 🎯 Test Categories

```bash
# Run all tests
python SolutionController.py both "🧪 Run CTest" default Debug

# Unit tests only
ctest --preset debug-linux-x86_64-gcc-15 --label-regex "unit"

# Integration tests
ctest --preset debug-linux-x86_64-gcc-15 --label-regex "integration"

# Performance benchmarks
ctest --preset debug-linux-x86_64-gcc-15 --label-regex "benchmark"
```

### 📊 Test Coverage

```bash
# Enable coverage during configuration
cmake --preset debug-linux-x86_64-gcc-15 -DENABLE_COVERAGE=ON

# Build with coverage
cmake --build --preset debug-linux-x86_64-gcc-15

# Run tests to generate coverage data
ctest --preset debug-linux-x86_64-gcc-15

# Generate HTML coverage report
make coverage-html
# or using cmake
cmake --build . --target coverage-html

# Generate XML coverage report (for CI/CD)
make coverage-xml
# or using cmake
cmake --build . --target coverage-xml   

# Generate both HTML and XML reports
make coverage
# or using cmake
cmake --build . --target coverage

# Display coverage summary in console
make coverage-summary
# or using cmake
cmake --build . --target coverage-summary

# Reset coverage counters
make coverage-reset
# or using cmake
cmake --build . --target coverage-reset

# Alternative: Direct gcovr usage
gcovr --html --html-details -o coverage.html
gcovr -x -o coverage.xml
```

---

## 📚 Library Development

### 📦 Library Structure

The template supports both header-only and compiled library development:

```cpp
// include/DotNameLib/DotNameLib.hpp
#pragma once

namespace DotNameLib {
    // Public API
    bool initialize();
    void shutdown();
    std::string getVersion();
}

// src/DotNameLib.cpp
#include "DotNameLib/DotNameLib.hpp"

namespace DotNameLib {
    bool initialize() {
        // Implementation
        return true;
    }
}
```

### 🔗 Integration Methods

1. You create your own project called **Wheels** *using DotNameCpp* and push it to GitHub.
2. Then, in your next project named **Car**, you use the **Wheels** library as follows:

#### Method 1: CPM.cmake (Recommended)

```cmake
# in project Car in file project-standalone.cmake
CPMAddPackage("gh:tomasmark79/Wheels#main")
target_link_libraries(${STANDALONE_NAME} PRIVATE WheelsLib CarLib cxxopts::cxxopts)

# in project Car in file project-tests.cmake
target_link_libraries(${TEST_NAME} PRIVATE GTest::gtest GTest::gtest_main WheelsLib dotname::${TEST_NAME_LOWER}_standalone_common)
```
```cpp
// in project Car in file AppCore.hpp
#include <WheelsLib/WheelsLib.hpp>
std::unique_ptr<dotname::WheelsLib> uniqueWheelsLib;
uniqueWheelsLib = std::make_unique<dotname::WheelsLib> (AppContext::assetsPath);
LOG_I_STREAM << "Wheels count: " << uniqueWheelsLib->getWheelsCount() << std::endl;
```

```bash
$ ./CarStandalone

# output
Starting CarStandalone ...
WheelsLib v.0.0.1 constructed ...
Assets: "tmp/Car/build/standalone/default/share/CarStandalone/assets"
path: "tmp/Car/build/standalone/default/share/CarStandalone/assets/DotNameLogoV2.svg"
CarLib v.0.0.1 constructed ...
Assets: "tmp/Car/build/standalone/default/share/CarStandalone/assets"
path: "tmp/Car/build/standalone/default/share/CarStandalone/assets/DotNameLogoV2.svg"
Wheels count: 4
CarLib v.0.0.1 ... destructed
This is a demo error message
Sucessfully exited CarStandalone
WheelsLib v.0.0.1 ... destructed
```

#### Method 2: FetchContent similar to CPM.cmake

```cmake
include(FetchContent)
FetchContent_Declare(
    Wheels
    GIT_REPOSITORY https://github.com/tomasmark79/Wheels.git
    GIT_TAG v1.0.0
)
FetchContent_MakeAvailable(Wheels)

target_link_libraries(your_target Wheels::Wheels)
```

#### Method 3: Conan Package - TODO

```python
# Create Conan package
python SolutionController.py both "⚔️ Create conan library recipe" noNeedArch

# In consumer project's conanfile.py
def requirements(self):
    self.requires("dotnamelib/1.0.0")
```

#### Method 4: Subdirectory

```cmake
add_subdirectory(path/to/Wheels)
target_link_libraries(your_target Wheels::Wheels)
```

#### Method 5: find_package

```cmake
find_package(Wheels REQUIRED)
target_link_libraries(your_target Wheels::Wheels)
```

### 📋 API Design Guidelines

- **Namespace Everything**: Use project-specific namespaces
- **RAII Pattern**: Prefer automatic resource management
- **Exception Safety**: Provide strong exception safety guarantees
- **ABI Stability**: Consider ABI compatibility for library updates
- **Documentation**: Comprehensive Doxygen documentation

### 🔄 Versioning Strategy

The main versioning for libraries is maintained in the project definition file at `cmake/project-library.cmake`.

```cmake
# Semantic versioning
set(PROJECT_VERSION_MAJOR 1)
set(PROJECT_VERSION_MINOR 0)
set(PROJECT_VERSION_PATCH 0)
set(PROJECT_VERSION "${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}.${PROJECT_VERSION_PATCH}")
```

---

## 🔄 CI/CD Pipeline

### 🚀 GitHub Actions Workflows

Comprehensive CI/CD with multi-platform support:

**Implemented Workflows:**
- **✅ Linux CI**: Ubuntu with GCC and Clang
- **✅ macOS CI**: Latest macOS with Xcode
- **✅ Windows CI**: Windows Server with MSVC
- **✅ Cross-Platform Testing**: Automated test execution
- **✅ Code Quality**: Static analysis and formatting checks
- **✅ Documentation**: Automated Doxygen generation
- **✅ Public Repository Sync**: Automated synchronization to public repo with `-Pub` suffix 

**Workflow Features:**
- Matrix builds across multiple compilers and configurations
- Conan dependency caching for faster builds
- Artifact collection for build outputs
- Code coverage reporting integration
- Release automation with semantic versioning
- Selective file synchronization to public repository

### 📢 Public Repository Automation

The template includes automated public repository synchronization via `make-pub.yml`:

- **Disabled by default**: Requires explicit developer activation
- **Enable sync**: Set `ENABLE_SYNC=true` in `.github/workflows/make-pub.conf`
- **Auto-sync**: Triggers on push to main branch (when enabled)
- **Selective files**: Configure via `.github/workflows/make-pub.conf`
- **Repository naming**: Creates `[ProjectName]-Pub` automatically
- **Token support**: Uses (PAT) `PUB_REPO_TOKEN` for authentication

**Badge Status**: See repository badges at the top of this README for current build status.

---

## 🛠️ Maintenance & Utilities

### 🔄 Project Maintenance Scripts

#### SolutionRenamer.py
Rename your project from the template:

```bash
python SolutionRenamer.py DotNameLib MyAwesomeLib DotNameStandalone MyAwesomeApp
python SolutionRenamer.py MyAwesomeLib DotNameLib MyAwesomeApp DotNameStandalone
```

Affected files:
- ✓ All CMake configuration files
- ✓ All C++ source files and headers
- ✓ VS Code configuration (`launch.json`, `tasks.json`)
- ✓ Documentation (`Doxyfile`, `README.md`)
- ✓ Package management (`conanfile.py`)
- ✓ Web assets (`ems-mini.html`)
- ✓ Logger configuration
- ✓ License files

#### SolutionUpgrader.py
Update template files from the upstream repository:

```bash
python SolutionUpgrader.py
```

#### SolutionController.py
Central automation hub for all build and development tasks:

```bash
# Interactive usage - Use VSCode tasks for full functionality
python SolutionController.py

# Command line usage
python SolutionController.py <product> "<task>" <architecture> [build_type]

# Examples:
python SolutionController.py standalone "🔨 Build" default Debug
python SolutionController.py both "🦸 Zero to Hero" default Release
python SolutionController.py emscripten "🚀 Launch Emscripten Server" noNeedArch

# Note: Help system documentation is in development
# For complete task list, use VSCode tasks menu (Shift+F7)
```

---

## 📖 Documentation

### 📚 Doxygen Integration

Automatic documentation generation with Doxygen:

```bash
# Generate documentation
python SolutionController.py both "📖 Doxygen documentation generation" noNeedArch
```

### 📱 View Documentation

```bash
# Open the generated documentation in your browser (Linux)
xdg-open doc/html/index.html
```

### 🔗 Additional Resources

- **API Reference**: Generated from source code comments
- **User Guide**: Comprehensive usage examples
- **Developer Guide**: Contribution guidelines and architecture
- **Changelog**: Version history and migration guides

---

## 📄 License

**MIT License**

Copyright (c) 2024-2025 Tomáš Mark

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## ⚠️ Important Disclaimer

This template is provided "as is" without warranties of any kind. While extensively tested across multiple platforms and continuously maintained, users must validate that the template meets their specific requirements before production use. The template undergoes regular updates to maintain compatibility with evolving toolchains and dependencies.

**Key Considerations:**
- Verify all dependencies and tools are compatible with your target environment
- Test thoroughly in your specific development and deployment scenarios  
- Some features (marked as TODO) are planned but not yet implemented
- Cross-platform builds may require additional configuration on certain systems

---

**Happy coding! 🚀🚀🚀**

For support, questions, or suggestions, please [open an issue](https://github.com/tomasmark79/DotNameCpp/issues) or [start a discussion](https://github.com/tomasmark79/DotNameCpp/discussions).

[🔝 Back to top](#dotnamecpp---advanced-c-development-template)

---

## 📢 Public Repository Information

This is a **public version** of the **DotNameCpp** project.

This repository contains carefully selected files from the main project that are suitable for public sharing and collaboration.

### 🔄 Automatic Synchronization

The content of this repository is automatically synchronized using GitHub Actions.

- **Last synchronization:** 2025-08-21 13:44:18 UTC
- **Source commit:** `3b1dd5b`
- **Synchronization rules:** Controlled by automated configuration

### 🤝 Contributing

If you find this project useful or have suggestions for improvement, feel free to:
- ⭐ Star this repository
- 🐛 Report issues or bugs
- 💡 Suggest new features
- 🔄 Submit pull requests

### 📞 Contact

For questions about this project or collaboration opportunities, please create an issue in this repository.