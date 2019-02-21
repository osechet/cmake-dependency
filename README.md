This is a simple repo to test the behavior of cmake's find_dependency command with and without conan package.

## Build

```
mkdir build
cd build
cmake .. -DCMAKE_PREFIX_PATH:PATH=/path/to/gtest
```
The output shows:
```
GTEST_FOUND = True
GTest_FOUND = True
```

With conan:
```
conan install gtest/1.8.1@bincrafters/stable
mkdir build
cd build
cmake .. -DCMAKE_PREFIX_PATH:PATH=/path/to/conan/gtest -DCMAKE_MODULE_PATH:PATH=/path/to/conan/gtest
```
With conan's invalid FindGTest script, the configure stops after the `find_dependency` call. There is no error but the configure is not complete and the build is not possible.
