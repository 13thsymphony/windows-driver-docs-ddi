---
UID: NC:d3d10umddi.PFND3D10DDI_FLUSH
title: PFND3D10DDI_FLUSH
author: windows-driver-content
description: The Flush(D3D10) function submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver.
old-location: display\flush_d3d10_.htm
old-project: display
ms.assetid: 846f8539-4cb3-41d5-836d-563b7eb0d70b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Flush, Flush callback function [Display Devices], PFND3D10DDI_FLUSH, UserModeDisplayDriverDx10_Functions_35acd3a9-af32-4a8f-b2d6-a4b12f3aebc4.xml, d3d10umddi/Flush, display.flush_d3d10_
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
-	Flush
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_FLUSH callback function
The <i>Flush(D3D10)</i> function submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver.

## Syntax

```
PFND3D10DDI_FLUSH Pfnd3d10ddiFlush;

void Pfnd3d10ddiFlush(
   D3D10DDI_HDEVICE
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`




## Return Value

None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

After the <i>Flush(D3D10)</i> function completes, all previously issued commands no longer depend on actions that occur within the application's user-mode context. In addition, applications can safely suspend themselves without blocking rendering until the kernel restarts them (such as, when an asynchronous query is used).

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>Flush(D3D10)</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>