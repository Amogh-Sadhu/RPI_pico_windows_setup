# Raspberrry pi Windows Setup
## A short guide to program and run rpi pico on a windows machine using vscode

### Things to download & install
[ARM GCC Compiler](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)   
[CMake](https://cmake.org/download/)  
[Build Tools for Visual Studio Code](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019)    
[Python](https://www.python.org/downloads/windows/)    
[Git](https://git-scm.com/download/win)  
[VScode](https://code.visualstudio.com/download)  


`While installing ARM gcc compiler, Cmake, Python, GIT, VScode make sure to select the Add to Path option.`  

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
Open the developer command prompt and run following commands
```
cd /pico
code
```
`Always open vscode this way to work with raspberrypi pico. Before proceding delete the contents of build folder.`  

Goto extensions tab in vscode and install CMake tools  

After installing CMake open setting by using shortcut ctrl+,  

Expand the Extensions option and select CMake Tool configuration option.  

Scroll and select `Cmake: Configure Environment` and set item as `PICO_SDK_PATH` and values as `..\..\pico-sdk`.  
Scroll down further until you find `Cmake: Generator`. Enter `NMake Makefiles` in the space below.   

Close the setting window and select `Explorer` tab on the top left and click on `Open Folder` option.  
Browse to c:\pico\pico-examples\ and select the folder.
Select yes when asked to configure project

image

