---
UID: NC:d3dumddi.PFND3DDDI_DECODEENDFRAME
title: PFND3DDDI_DECODEENDFRAME
author: windows-driver-content
description: The DecodeEndFrame function notifies the user-mode display driver that all of the data that was required to decode the current frame was submitted.
old-location: display\decodeendframe.htm
old-project: display
ms.assetid: 6e8d3280-6ddc-4593-9208-c4f0c9ff254c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DecodeEndFrame, DecodeEndFrame callback function [Display Devices], PFND3DDDI_DECODEENDFRAME, UserModeDisplayDriver_Functions_c80e307b-2b64-4b43-84c3-cae711e8282f.xml, d3dumddi/DecodeEndFrame, display.decodeendframe
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
-	DecodeEndFrame
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DECODEENDFRAME callback function
The <b>DecodeEndFrame</b> function notifies the user-mode display driver that all of the data that was required to decode the current frame was submitted.

## Syntax

```
PFND3DDDI_DECODEENDFRAME Pfnd3dddiDecodeendframe;

HRESULT Pfnd3dddiDecodeendframe(
  HANDLE hDevice,
  D3DDDIARG_DECODEENDFRAME *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<b>DecodeEndFrame</b> returns one of the following values:

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
Decoding successfully completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
DecodeEndFrame could not allocate the required memory for it to complete.

</td>
</tr>
</table>

## Remarks

The <b>DecodeEndFrame</b> function notifies the user-mode display driver that its <a href="https://msdn.microsoft.com/e12496c0-e3e4-437e-9f84-a30ee99b4541">DecodeExecute</a> function can no longer be called on the specified decode device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542991">D3DDDIARG_DECODEENDFRAME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/e12496c0-e3e4-437e-9f84-a30ee99b4541">DecodeExecute</a>