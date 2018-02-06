---
UID: NS:d3d10umddi.D3D10_2DDI_ADAPTERFUNCS
title: D3D10_2DDI_ADAPTERFUNCS
author: windows-driver-content
description: The D3D10_2DDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object.
old-location: display\d3d10_2ddi_adapterfuncs.htm
old-project: display
ms.assetid: b8ccd6f0-d1bf-430f-bffb-dd161793096f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D10_2DDI_ADAPTERFUNCS structure [Display Devices], d3d10umddi/D3D10_2DDI_ADAPTERFUNCS, D3D10_2DDI_ADAPTERFUNCS, display.d3d10_2ddi_adapterfuncs, UMDisplayDriver_Dx11param_Structs_6d47bf5d-d3ef-4187-83a0-95d5c3c62413.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_2DDI_ADAPTERFUNCS is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10_2DDI_ADAPTERFUNCS
product: Windows
targetos: Windows
req.typenames: D3D10_2DDI_ADAPTERFUNCS
---

# D3D10_2DDI_ADAPTERFUNCS structure
The D3D10_2DDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object.

## Syntax
````
typedef struct D3D10_2DDI_ADAPTERFUNCS {
  PFND3D10DDI_CALCPRIVATEDEVICESIZE  pfnCalcPrivateDeviceSize;
  PFND3D10DDI_CREATEDEVICE           pfnCreateDevice;
  PFND3D10DDI_CLOSEADAPTER           pfnCloseAdapter;
  PFND3D10_2DDI_GETSUPPORTEDVERSIONS pfnGetSupportedVersions;
  PFND3D10_2DDI_GETCAPS              pfnGetCaps;
} D3D10_2DDI_ADAPTERFUNCS;
````

## Members


`pfnCalcPrivateDeviceSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedevicesize.md">CalcPrivateDeviceSize</a> function that specifies the size of a memory block that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data.

`pfnCloseAdapter`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_closeadapter.md">CloseAdapter(D3D10)</a> function that releases resources for a graphics adapter object.

`pfnCreateDevice`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function that creates a representation of a display device that handles a collection of rendering state.

`pfnGetCaps`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function that queries for capabilities of the graphics hardware.

`pfnGetSupportedVersions`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getsupportedversions.md">GetSupportedVersions</a> function that retrieves the version of the operating system that the driver supports and the hardware capabilities that are available (for example, Direct3D version 10.0, Direct3D version 10.1, and so on).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3D10_2DDI_ADAPTERFUNCS is supported beginning with the Windows 7 operating system. D3D10_2DDI_ADAPTERFUNCS is supported beginning with the Windows 7 operating system. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_closeadapter.md">CloseAdapter(D3D10)</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getsupportedversions.md">GetSupportedVersions</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_openadapter.md">D3D10DDIARG_OPENADAPTER</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedevicesize.md">CalcPrivateDeviceSize</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openadapter.md">OpenAdapter10</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_2DDI_ADAPTERFUNCS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>