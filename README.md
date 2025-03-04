# Qualisys Realtime SDK

C++ package with SDK and examples

## Build with Visual Studio

Build RTClientSDK solution in Visual Studio 2017.

## Build with CMake (Windows & Linux)

* Tested with GCC 13.3.0
* Tested with Clang 18.1.3
* Tested with VS 2017 / MSVC 19.42

### Cloning the Repository

`git clone https://github.com/qualisys/qualisys_cpp_sdk.git`

### Build As Static
```
cmake -S . -B build -Dqualisys_cpp_sdk_OUTPUT_TYPE=STATIC && cmake --build build --config Release
```

### Build As Shared/Dynamic
```
cmake -S . -B build -Dqualisys_cpp_sdk_OUTPUT_TYPE=SHARED && cmake --build build --config Release
```

### Build As Shared/Dynamic (With Versioning)
```
cmake -S . -B build -Dqualisys_cpp_sdk_OUTPUT_TYPE=SHARED_VERSIONED && cmake --build build --config Release
```

### Build Examples
```
cmake -S . -B build -Dqualisys_cpp_sdk_BUILD_EXAMPLES=ON && cmake --build build --config Release
```

### Build & Run Tests
```
cmake -S . -B build -Dqualisys_cpp_sdk_BUILD_TESTS=ON && cmake --build build --config Release
ctest --test-dir build
```

### Install (After Build)
Default:
```
cmake --install build --config Release
```
Specify Target Path:
```
cmake --install build --prefix <install_path> --config Release
```

## Usage

Include the Qualisys SDK in your CMake application:

```cmake
find_package(qualisys_cpp_sdk REQUIRED)

target_link_libraries(myapplication PRIVATE qualisys_cpp_sdk)
```