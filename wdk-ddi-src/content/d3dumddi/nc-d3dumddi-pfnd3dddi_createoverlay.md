---
UID: NC:d3dumddi.PFND3DDDI_CREATEOVERLAY
title: PFND3DDDI_CREATEOVERLAY
author: windows-driver-content
description: The CreateOverlay function allocates overlay hardware and makes the overlay visible.
old-location: display\createoverlay.htm
old-project: display
ms.assetid: 761377ff-95a6-426b-8372-3f347870f9c4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CreateOverlay, CreateOverlay callback function [Display Devices], PFND3DDDI_CREATEOVERLAY, UserModeDisplayDriver_Functions_8418bf74-3398-4913-9002-2f0b2a0941fb.xml, d3dumddi/CreateOverlay, display.createoverlay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	CreateOverlay
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_CREATEOVERLAY callback function
The <b>CreateOverlay</b> function allocates overlay hardware and makes the overlay visible.

## Syntax

```
PFND3DDDI_CREATEOVERLAY Pfnd3dddiCreateoverlay;

HRESULT Pfnd3dddiCreateoverlay(
  HANDLE hDevice,
  D3DDDIARG_CREATEOVERLAY *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<b>CreateOverlay</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The overlay is successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/761377ff-95a6-426b-8372-3f347870f9c4">CreateOverlay</a> could not complete because of insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/761377ff-95a6-426b-8372-3f347870f9c4">CreateOverlay</a> could not complete because insufficient bandwidth was available or the requested overlay hardware was unavailable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_UNSUPPORTEDOVERLAYFORMAT</b></dt>
</dl>
</td>
<td width="60%">
The specified overlay format is not supported by the overlay hardware. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_UNSUPPORTEDOVERLAY</b></dt>
</dl>
</td>
<td width="60%">
The overlay hardware is not supported for the specified size and display mode. 

</td>
</tr>
</table>

## Remarks

Overlays are independent from the resources that are displayed by using the overlays.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542948">D3DDDIARG_CREATEOVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>