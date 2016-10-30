# OpenCV for Windows
### OpenCV build for .Net and UWP.


The sole purpose of this project is to create a nuget package for OpenCV.
The nuget package includes C++ binaries on Windows, which should be usable from .Net and UWP apps.


## Native Version

Currently, the nuget build spec uses some conventions which you need to follow (partly due to the limitations in the tool).

You can just use pre-built nuget packages. But, in general, you may want to build your own version of OpenCV (using your preferred/optimized configurations). If you want to distribute your builds via NuGet (e.g., for internal use), then here's what you need to do:

1. Install the [CoApp PowerShell tool](http://coapp.org/pages/releases.html).
1. Build OpenCV and use the directories, "opencv-build-x86", "opencv-build-x64", etc., as a sibling to the cvwin root directory.
1. Add all include files under "opencv-dist". This can be downloaded from cvwin/opencv-dist project. But, this may be outdated. Use your own distribution (binary build), if necessary. All you need is the _include_ directory.
1. Update opencv.win.native.autopkg to suit your project definitions. At minimum, you may want to change the _nuspec.id_ to avoid conflicts.
1. Run _write-nugetpackage opencv.win.native.autopkg_ from the native directory.
1. You can push nuget packages using `neget` CLI:
    NuGet push [nupkg file apth] [api key] -NoSymbols -Timeout 3000 -Source nuget.org


### Pre-Built Binaries

You can install pre-built OpenCV binaries from NuGet Gallery using Package Manager:

    Install-Package opencv.win.native 



_Note:_ The current distribution on the NuGet Gallery repository only includes binaries for x86 and x64 (for Visual Studio 2015), but not for ARM.




## C++/CLI Wrapper Library ("Universal DLLs")

_Coming soon_


## C++/CX Wrapper Library (for .Net Core)

_Coming soon_



## Copyright

* [OpenCV for Windows 2016](https://github.com/cvwin)
