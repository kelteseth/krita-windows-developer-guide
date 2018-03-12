## Start developing Krita on Windows in 5 minutes with MSYS2

### 1 Pre Requirements

Download and install MSYS2 x86\_x64 from [http://www.msys2.org/](http://www.msys2.org/)

- Start MSYS2
- Update the repositories
  - Run: pacman -Syu
  - Restart terminal. **Ignore** these errors:

"warning: terminate MSYS2 without returning to shell and check for updates again. warning: for example close your terminal window instead of calling exit"

There is a bug if you want to close the window it crashes. Nonetheless it should work!
  - Run: pacman -Su
  - Wait for the updates to be installed

### 2 Install Dependencies

- We cheat here because this can take some time depending on your internet connection and you don&#39;t have to do anything :)
  - Run:

```js
pacman -S 
mingw64/mingw-w64-x86_64-karchive-qt5 
mingw64/mingw-w64-x86_64-kconfig-qt5 
mingw64/mingw-w64-x86_64-kwidgetsaddons-qt5 
mingw64/mingw-w64-x86_64-kcompletion-qt5 
mingw64/mingw-w64-x86_64-kcoreaddons-qt5 
mingw64/mingw-w64-x86_64-kguiaddons-qt5 
mingw64/mingw-w64-x86_64-ki18n-qt5 
mingw64/mingw-w64-x86_64-kitemmodels-qt5 
mingw64/mingw-w64-x86_64-kitemviews-qt5 
mingw64/mingw-w64-x86_64-kwindowsystem-qt5 
mingw64/mingw-w64-x86_64-extra-cmake-modules 
mingw64/mingw-w64-x86_64-gcc 
mingw64/mingw-w64-x86_64-gdb  
mingw64/mingw-w64-x86_64-qt5  
mingw64/mingw-w64-x86_64-qt-creator 
mingw64/mingw-w64-x86_64-libwinpthread-git 
mingw64/mingw-w64-x86_64-winpthreads-git 
mingw64/mingw-w64-x86_64-libpng 
mingw64/mingw-w64-x86_64-boost 
mingw64/mingw-w64-x86_64-gsl 
mingw64/mingw-w64-x86_64-zlib 
mingw64/mingw-w64-x86_64-openexr 
mingw64/mingw-w64-x86_64-ilmbase 
mingw64/mingw-w64-x86_64-libtiff 
mingw64/mingw-w64-x86_64-libraw 
mingw64/mingw-w64-x86_64-opencolorio-git 
mingw64/mingw-w64-x86_64-eigen3 
mingw64/mingw-w64-x86_64-gexiv2 
mingw64/mingw-w64-x86_64-lcms2 
mingw64/mingw-w64-x86_64-poppler 
mingw64/mingw-w64-x86_64-openjpeg2 
mingw64/mingw-w64-x86_64-libjpeg-turbo 
mingw64/mingw-w64-x86_64-gsl
mingw64/mingw-w64-x86_64-opencolorio-git
git

```
### 3 Download Krita via git

- Open MSYS2 shell
- Run: cd to/your/desired/destination
- Run: git clone git://anongit.kde.org/krita
- You also could use a GUI for this like [GitExtentions](https://github.com/gitextensions/gitextensions/releases)!

### 4 Compiling Krita

1. Start QtCreator (C:\msys64\mingw64\bin\qtcreator.exe)  and open the CMakeLists.txt from the krita folder via "Open Project"
2.Configure the project as 64bit. Click Configure project
3. Wait for "CMake Project was parsed successfully" in the General Message tab. This can take some time!


4. Go to "Projects" on the left and under &quot;Build Steps&quot;
    1. Change the CMAKE\_INSTALL\_PREFIX to a writable location like next to your source code! This is due to how plugins work in Krita [More info here!](https://www.reddit.com/r/krita/comments/7m3hnn/ive_made_a_quick_guide_for_developing_krita_on/drrthbz/)
    2. Press the "Add Build Step" Button
        1. Select Build in the dropdown
        2. remove the all checkbox and enable the install checkbox
5. Compile via the big green arrow on the bottom left
6. Compiling can take quite some time. It takes at least 15-20 minutes on my 8 Core Ryzen 1700
7. Happy Hacking!

//Optional add the bin folder to your windows path to open Qtcreator via windows search ;)
C:\msys64\mingw64\bin

