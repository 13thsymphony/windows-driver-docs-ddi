---
UID: NC:d3dumddi.PFND3DDDI_GETCAPTUREALLOCATIONHANDLE
title: PFND3DDDI_GETCAPTUREALLOCATIONHANDLE
author: windows-driver-content
description: The GetCaptureAllocationHandle function maps the given capture resource handle to a kernel-mode allocation handle.
old-location: display\getcaptureallocationhandle.htm
old-project: display
ms.assetid: fb12a12b-6fb7-46d4-aa71-4c88d34d6ff9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: GetCaptureAllocationHandle, GetCaptureAllocationHandle callback function [Display Devices], PFND3DDDI_GETCAPTUREALLOCATIONHANDLE, UserModeDisplayDriver_Functions_839ce10f-1df9-4d62-a877-d64215b82370.xml, d3dumddi/GetCaptureAllocationHandle, display.getcaptureallocationhandle
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
-	GetCaptureAllocationHandle
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_GETCAPTUREALLOCATIONHANDLE callback function
The <i>GetCaptureAllocationHandle</i> function maps the given capture resource handle to a kernel-mode allocation handle.

## Syntax

```
PFND3DDDI_GETCAPTUREALLOCATIONHANDLE Pfnd3dddiGetcaptureallocationhandle;

HRESULT Pfnd3dddiGetcaptureallocationhandle(
  HANDLE hDevice,
  D3DDDIARG_GETCAPTUREALLOCATIONHANDLE *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>GetCaptureAllocationHandle</i> returns one of the following values:

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
The given resource is in GPU-accessible memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>GetCaptureAllocationHandle</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543154">D3DDDIARG_GETCAPTUREALLOCATIONHANDLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>