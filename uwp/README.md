# OpenCV for Windows
### OpenCV builds for UWP.

_Note: This repo is currently undergoing re-organization._


The sole purpose of this project is to create nuget packages for OpenCV.
The nuget packages include C++ native binaries on Windows 10, which can be used with UWP apps.


I built UWP version of nuget packages for OpenCV release 3.1.0, and put them in Nuget Gallery.
There are currenly 15 packages, one for each module.

You can install them using Package Manager.
For instance, 

    Install-Package OpenCV.Win.Core
    Install-Package OpenCV.Win.ImgProc
    ...

Search for ["OpenCV.Win UWP" on Nuget Gallery](https://www.nuget.org/packages?q=OpenCV.Win+UWP) for all 15 modules.




## Copyright

* [OpenCV for Windows 2016](https://github.com/cvwin)
