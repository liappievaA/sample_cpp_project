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


