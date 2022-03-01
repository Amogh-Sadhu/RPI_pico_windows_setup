# Raspberrry pi Windows Setup
## A short guide to program and run rpi pico on a windows machine using vscode

### Things to download
[ARM GCC Compiler](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)   
[CMake](https://cmake.org/download/)  
[Build Tools for Visual Studio Code](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019)    
[Python](https://www.python.org/downloads/windows/)    
[Git](https://git-scm.com/download/win)  

`While installing ARM gcc compiler, Cmake, Python, GIT make sure to select the Add to Path option.`  

### Donwload the pico sdk and pico example in following command in cmd 
```
git clone -b master https://github.com/raspberrypi/pico-sdk.git  
git clone -b master https://github.com/raspberrypi/pico-examples.git  
```
Download above folders into a folder named `pico` and place that folder in C:/  

From start menu open "Developer Command Prompt for VS 2019"  
Run following commands :
```
cd /pico/pico-sdk  
git submodule update -init
setx PICO_SDK_PATH “..\..\pico-sdk"
```
Restart the Developer prompt so that the the path gets updated.  

Run following commands to build the makefiles  
```
cd /pico/pico-examples
mkdir build
cd build
cmake -G “NMake Makefiles” ..
```


