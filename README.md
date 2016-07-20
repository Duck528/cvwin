# OpenCV for Windows
### OpenCV build for .Net and UWP.


The sole purpose of this project is to create a nuget package for OpenCV.
The nuget package includes C++ binaries on Windows, which should be usable from .Net and UWP apps.


## Native Version

Currently, the nuget build spec uses some conventions (partly due to the limitations in the tool).

You can just use pre-built nuget packages. But, in general, you may want to build your own version of OpenCV ( using your preferred configurations). If you want to distribute your builds via NuGet (e.g., for internal use), then here's what you need to do:

1. Install CoApp PowerShell tool.
1. Build OpenCV and use the directories, "opencv-build-x86", "opencv-build-x64", etc., as a sibling to the cvwin root directory.
1. Add all include files under "opencv-dist". This can be downloaded from cvwin/opencv-dist project. But, this may be outdated. Use your own distribution (binary build), if necessary.
1. Run _write-nugetpackage opencv.win.native.autopkg_ from the native directory.



_Note:_ The current distribution on NuGet repository only includes binaries for x86 and x64 (for Visual Studio 2015), but not for ARM.


## C++/CLI Wrapper Library ("Universal DLLs")

_Coming soon_


## Copyright

* [OpenCV for Windows 2016](https://github.com/cvwin)
