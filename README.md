# OpenCV for Windows
### OpenCV build for .Net and UWP.

_Note: All repos under the 'cvwin organization' on GitHub are currently being re-organized. Meanwhile, please download pre-built nuget packages for OpenCV 3 from Nuget Gallery._


The sole purpose of this project is to create nuget packages for OpenCV.
The nuget packages include C++ binaries on Windows, which should be usable from Win32, .Net, and/or UWP apps.


## Native Version (Win32)

Currently, the nuget build spec uses some conventions which you need to follow (partly due to the limitations in the tool).

You can just use pre-built nuget packages. But, in general, you may want to build your own version of OpenCV (using your preferred/optimized configurations). If you want to distribute your builds via NuGet (e.g., for internal use), then here's what you need to do:

1. Install the [CoApp PowerShell tool](http://coapp.org/pages/releases.html).
1. Build OpenCV and use the directories, "opencv-build-x86", "opencv-build-x64", etc., as a sibling to the cvwin root directory.
1. Add all include files under "opencv-dist". This can be downloaded from cvwin/opencv-dist project. But, this may be outdated. Use your own distribution (binary build), if necessary. All you need is the _include_ directory.
1. Update opencv.win.native.autopkg to suit your project definitions. At minimum, you may want to change the _nuspec.id_ to avoid conflicts.
1. Run _write-nugetpackage opencv.win.native.autopkg_ from the native directory.
1. You can push nuget packages using `nuget` CLI:

    NuGet push [nupkg file path] [api key] -NoSymbols -Timeout 3000 -Source nuget.org



### Pre-Built Binaries

You can install [pre-built OpenCV binaries (DLLs)](https://www.nuget.org/packages/opencv.win.native) from NuGet Gallery using Package Manager:

    Install-Package opencv.win.native 



_Note:_ The current distribution on the NuGet Gallery repository only includes binaries for x86 and x64 (for Visual Studio 2015), but not for ARM.


There are also [static library versions for OpenCV Win32](https://www.nuget.org/packages/opencv.win.native.static):

    Install-Package opencv.win.native.static




## C++/CLI Wrapper Library ("Universal DLLs")

_Coming soon_


## C++/CX Wrapper Library (for .Net Core)

_Coming soon_




## UWP Version

OpenCV can be built to be used in UWP apps on Windows 10 devices. 
Once you build "UWP-compatible" libraries, you can package them into nuget pakcages, if desired.
You can find some example nuspec files under the _uwp_ directory.

(I'll write more detailed how-to guide later. Please ping me if you need help.)



### Pre-Built Packages

I built UWP version of nuget packages for OpenCV release 3.1.0, and put them in Nuget Gallery.
There are currenly 15 packages, one for each module.

You can install them using Package Manager.
For instance, 

    Install-Package OpenCV.Win.Core
    Install-Package OpenCV.Win.ImgProc
    ...

Search for ["OpenCV.Win UWP" on Nuget Gallery](https://www.nuget.org/packages?q=OpenCV.Win+UWP) for all 15 modules.


Note that _VideoIO,_ and all dependent modules, require UWP Desktop extensions,
and those modules (or, at least certain features from VideoIO) cannot be used with other Windows 10 devices like Windows Phone or HoloLens.




## Copyright

* [OpenCV for Windows 2016](https://github.com/cvwin)
