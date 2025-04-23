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

# License GPLv3

    Copyright (C) 2023  Shuang Chen

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.

# License MIT

    Copyright (c) 2023 Chen Shuang

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

