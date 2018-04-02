---
UID: NC:d3d10umddi.PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE
title: PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE
author: windows-driver-content
description: The CalcDeferredContextHandleSize function queries for the amount of storage space that the driver requires to satisfy deferred context handles to the given immediate context object.
old-location: display\calcdeferredcontexthandlesize.htm
old-project: display
ms.assetid: d26c26ef-be8e-434a-b3d3-623ed539c541
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CalcDeferredContextHandleSize, CalcDeferredContextHandleSize callback function [Display Devices], PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE, UserModeDisplayDriverDx11_Functions_f5e77e2c-2925-4556-b80a-84636a4b326a.xml, d3d10umddi/CalcDeferredContextHandleSize, display.calcdeferredcontexthandlesize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcDeferredContextHandleSize is supported beginning with the Windows 7 operating system.
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
-	CalcDeferredContextHandleSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE callback function
The <b>CalcDeferredContextHandleSize</b> function queries for the amount of storage space that the driver requires to satisfy deferred context handles to the given immediate context object.

## Syntax

```
PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE Pfnd3d11ddiCalcdeferredcontexthandlesize;

SIZE_T Pfnd3d11ddiCalcdeferredcontexthandlesize(
   D3D10DDI_HDEVICE,
   D3D11DDI_HANDLETYPE,
  VOID *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D11DDI_HANDLETYPE`



`*`




## Return Value

<b>CalcDeferredContextHandleSize</b> returns the size of the storage space that the driver requires for the deferred context handles to the object that <b>pICObject</b> points to.

## Remarks

The driver is only required to implement <b>CalcDeferredContextHandleSize</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542163">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a> function.

The Direct3D runtime does not call the <b>CalcDeferredContextHandleSize</b> function from function tables for the deferred context. The runtime calls <b>CalcDeferredContextHandleSize</b> from the function table for the immediate context.

For more information about how <b>CalcDeferredContextHandleSize</b> is used, see <a href="https://msdn.microsoft.com/1b3e5c29-9b9e-4c10-8fe0-706255c8fd91">Using Context-Local DDI Handles</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | CalcDeferredContextHandleSize is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542152">D3D11DDI_HANDLETYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542163">D3D11DDI_THREADING_CAPS</a>



<a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a>