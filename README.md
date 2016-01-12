# AMD DX11 Separable Filter Sample
<img src="separablefilter11/media/Thumbnail.png" width="480" height="280" />

This sample presents a technique for achieving highly optimized, user-defined separable filters. It utilizes Direct3D 11 APIs and hardware to make use of DirectCompute 5.0 to greatly accelerate this common post processing technique. Included in the sample are implementations for the classic Gaussian filter, and also a fairly simple bilateral filter, but the shader and source code have been setup to allow the user to add their own different filters, with the minimum of fuss. The application implements both a Compute Shader and Pixel Shader path, so that the performance gains achieved through using DirectCompute can be measured.

### Prerequisites
* AMD Radeon&trade; GCN-based GPU (HD 7000 series or newer)
* 64-bit Windows 7 (SP1 with the [Platform Update](https://msdn.microsoft.com/en-us/library/windows/desktop/jj863687.aspx)), Windows 8.1, or Windows 10
* Visual Studio 2012, Visual Studio 2013, or Visual Studio 2015

### Getting Started
* Visual Studio solutions for VS2012, VS2013, and VS2015 can be found in the `separablefilter11\build` directory.
* Additional documentation can be found in the `separablefilter11\doc` directory.

### Premake
The Visual Studio projects in the `separablefilter11\build` directory were generated with Premake. To generate the project files yourself (for another version of Visual Studio, for example), open a command prompt in the `premake` directory and execute the following command:

* `update_vs_files_for_dx11_sample.bat separablefilter11 [action]`
* For example: `update_vs_files_for_dx11_sample.bat separablefilter11 vs2010`

This version of Premake has been modified from the stock version to use the property sheet technique for the Windows SDK from this [Visual C++ Team blog post](http://blogs.msdn.com/b/vcblog/archive/2012/11/23/using-the-windows-8-sdk-with-visual-studio-2010-configuring-multiple-projects.aspx). The technique was originally described for using the Windows 8.0 SDK with Visual Studio 2010, but it applies more generally to using newer versions of the Windows SDK with older versions of Visual Studio.

The default SDK for a particular version of Visual Studio (for 2012 or higher) is installed as part of Visual Studio installation. This default (Windows 8.0 SDK for Visual Studio 2012 and Windows 8.1 SDK for Visual Studio 2013) will be used if newer SDKs do not exist on the user's machine. However, the projects generated with this version of Premake will use the next higher SDK (Windows 8.1 SDK for Visual Studio 2012 and Windows 10 SDK with Visual Studio 2013), if the newer SDKs exist on the user's machine. For Visual Studio 2015, this version of Premake adds the WindowsTargetPlatformVersion element to the project file so that the Windows 10 SDK will be used.

### Third-Party Software
* DXUT is distributed under the terms of the MIT License. See `dxut\MIT.txt`.
* Premake is distributed under the terms of the BSD License. See `premake\LICENSE.txt`.
