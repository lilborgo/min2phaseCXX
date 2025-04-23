# min2phase C++
- Rubik's Cube solver or scrambler.
- [Algorithm](Algorithm.md)
- [Benchmarks](Benchmarks.md)

# Usage

First, you need to initialize the algorithm using:
```C++
    min2phase::init();
```
After that, you can write the initialization into a file, so the next time the algorithm initialization will be faster. Using:
```C++
    min2phase::writeFile("name.m2pc");
```
Now, the next time you can load the coordinates from the file:
```C++
    min2phase::loadFile("name.m2pc");
```
If you try to load a file that does not exist, min2phase::init() will be executed automatically.

After the initialization, you can execute the solver. This is an example of how it works.
See [min2phase.h](include/min2phase/min2phase.h) for the arguments explanation of the solver.

```C++
#include <iostream>
#include <min2phase/min2phase.h>
#include <min2phase/tools.h>

int main(int argc, char *argv[]){

    min2phase::init();//precomputed coordinates

    std::cout << min2phase::solve(min2phase::tools::randomCube(), 21, 1000000, 0, min2phase::APPEND_LENGTH | min2phase::USE_SEPARATOR, nullptr);
    return 0;
}
```
See [tools.h](include/min2phase/tools.h) for some useful function for the solver.
You can also read the coordinates from a file, see [min2phase.h](include/min2phase/min2phase.h). Reading from a file the coordinates will increase the speed of the algorithm.


# Compiling

```bash
cmake CMakeLists.txt
make
g++ -I include/ yourporgram.cpp -L. -lmin2phase -o yourporgram -Wl,-rpath,.
```

# License

This software is distributed on MIT, more information available in [LICENSE.md](LICENSE.md).
