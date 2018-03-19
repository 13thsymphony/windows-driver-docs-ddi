---
UID: NC:d3dumddi.PFND3DDDI_UPDATEOVERLAYCB
title: PFND3DDDI_UPDATEOVERLAYCB
author: windows-driver-content
description: The pfnUpdateOverlayCb function modifies a kernel-mode overlay object.
old-location: display\pfnupdateoverlaycb.htm
old-project: display
ms.assetid: 17f89cea-350c-43f6-a60d-32fc2d299dd7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3Druntime_Functions_9a6ce628-61ad-4c22-9fa7-aa2c83e680b6.xml, PFND3DDDI_UPDATEOVERLAYCB, d3dumddi/pfnUpdateOverlayCb, display.pfnupdateoverlaycb, pfnUpdateOverlayCb, pfnUpdateOverlayCb callback function [Display Devices]
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
-	pfnUpdateOverlayCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_UPDATEOVERLAYCB callback function
The <b>pfnUpdateOverlayCb</b> function modifies a kernel-mode overlay object.

## Syntax

```
PFND3DDDI_UPDATEOVERLAYCB Pfnd3dddiUpdateoverlaycb;

HRESULT Pfnd3dddiUpdateoverlaycb(
  HANDLE hDevice,
  CONST D3DDDICB_UPDATEOVERLAY *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<b>pfnUpdateOverlayCb</b> returns one of the following values:

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
The overlay object was successfully modified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>
</td>
<td width="60%">
<b>pfnUpdateOverlayCb</b> failed because of a lack of overlay hardware or bandwidth.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<b>pfnUpdateOverlayCb</b> could not allocate memory that was required for it to complete.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_updateoverlay.md">D3DDDICB_UPDATEOVERLAY</a>