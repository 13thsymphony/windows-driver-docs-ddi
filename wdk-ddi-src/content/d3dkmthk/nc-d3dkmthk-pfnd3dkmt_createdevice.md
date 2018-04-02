---
UID: NC:d3dkmthk.PFND3DKMT_CREATEDEVICE
title: PFND3DKMT_CREATEDEVICE
author: windows-driver-content
description: The D3DKMTCreateDevice function creates a kernel-mode device context.
old-location: display\d3dkmtcreatedevice.htm
old-project: display
ms.assetid: 91f559cc-c84b-450d-b52c-8289e976f991
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTCreateDevice, D3DKMTCreateDevice callback function [Display Devices], OpenGL_Functions_09099f43-bae3-4859-9465-434915af774a.xml, PFND3DKMT_CREATEDEVICE, d3dkmthk/D3DKMTCreateDevice, display.d3dkmtcreatedevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
-	d3dkmthk.h
api_name:
-	D3DKMTCreateDevice
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---


# PFND3DKMT_CREATEDEVICE callback function
The <b>D3DKMTCreateDevice</b> function creates a kernel-mode device context.

## Syntax

```
PFND3DKMT_CREATEDEVICE Pfnd3dkmtCreatedevice;

NTSTATUS Pfnd3dkmtCreatedevice(
  D3DKMT_CREATEDEVICE *
)
{...}
```

## Parameters

`*`




## Return Value

<b>D3DKMTCreateDevice</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The device context was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546836">D3DKMTCreateDevice</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547819">D3DKMT_CREATEDEVICE</a>