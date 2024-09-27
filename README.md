To create folder build
```console
PS> cmake -B build/ -S . -G "MinGW Makefiles"
```
To compile
```console
PS> cmake --build build/
```
To create hidden folder git
```console
PS> git init
```
To show git the files in which we want to see changes we need to create file .gitignore and whire there:
```console
PS> *.swp
PS> build
```
And to add this new file to git
```console
PS> git add .
```
To see the changes 
```console
PS> git status
```
To commit the changes 
```console
PS> git commit -m 'initial commit'
```
To see all commits
```console
PS> git log
```
To push
```console 
PS> git push -u origin master 
```
If we change file CMakeLists.txt we need to whire
```console
PS> git add CMakeLists.txt
PS> git commit -m 'cmake minimum version lower'
PS> git push
```
#### Github Action
Create a folder .github, there create a folder workflows, then create a file test.yaml

Instead of write evety time ...
```console
cd build/
cmake ..
cmake --build .
./main 45
```
... we can customize cmake in github action

#### Unit tests

We can use googletest or Boost.Test

First we need to install googletest
```console
PS> git clone https://github.com/google/googletest.git -b v1.15.2
PS> cd googletest/
PS> mkdir build/
PS> cmake -G "MinGW Makefiles" --install-prefix "C:\Program Files (x86)\googletest-distribution" ..
PS> cd..
PS> cmake --install build --prefix '/c/Program Files (x86)/googletest-distribution'
```
For my computer I need to add next lines in all CmakeLists.txt
```cmake
set( CMAKE_CXX_COMPILER "/msys64/ucrt64/bin/g++.exe" )
set( CMAKE_C_COMPILER "/msys64/ucrt64/bin/gcc.exe" )
```
##### Then we need to write tests
First, create a file "test_add.cpp" and add in test.yaml - run: ./build/tests