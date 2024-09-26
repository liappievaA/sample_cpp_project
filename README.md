To create folder build
```console
cmake -B build/ -S . -G "MinGW Makefiles"
```
To compile
```console
cmake --build build/
```
To create hidden folder git
```console
git init
```
To show git the files in which we want to see changes we need to create file .gitignore and whire there:
```console
*.swp
build
```
And to add this new file to git
```console
git add .
```
To see the changes 
```console
git status
```
To commit the changes 
```console
git commit -m 'initial commit'
```
To see all commits
```console
git log
```
To push
```console 
git push -u origin master 
```
If we change file CMakeLists.txt we need to whire
```console
git add CMakeLists.txt
git commit -m 'cmake minimum version lower'
git push
```
#### Github Action