---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEDEVICESIZE
title: PFND3D10DDI_CALCPRIVATEDEVICESIZE
author: windows-driver-content
description: The CalcPrivateDeviceSize function determines the size of a memory region that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data.
old-location: display\calcprivatedevicesize.htm
old-project: display
ms.assetid: 8221a99a-1b46-48ba-8930-ac973e009eee
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateDeviceSize, CalcPrivateDeviceSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEDEVICESIZE, UserModeDisplayDriverDx10_Functions_0de51abc-5fe3-4d65-bd0a-cc4f32f08d81.xml, d3d10umddi/CalcPrivateDeviceSize, display.calcprivatedevicesize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CalcPrivateDeviceSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_CALCPRIVATEDEVICESIZE callback function
The <b>CalcPrivateDeviceSize</b> function determines the size of a memory region that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data.

## Syntax

```
PFND3D10DDI_CALCPRIVATEDEVICESIZE Pfnd3d10ddiCalcprivatedevicesize;

SIZE_T Pfnd3d10ddiCalcprivatedevicesize(
   D3D10DDI_HADAPTER,
  CONST D3D10DDIARG_CALCPRIVATEDEVICESIZE *
)
{...}
```

## Parameters

`D3D10DDI_HADAPTER`



`*`




## Return Value

<b>CalcPrivateDeviceSize</b> returns the size of the memory region that the driver requires to store frequently-accessed data.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_calcprivatedevicesize.md">D3D10DDIARG_CALCPRIVATEDEVICESIZE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CALCPRIVATEDEVICESIZE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>