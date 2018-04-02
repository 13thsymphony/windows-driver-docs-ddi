---
UID: NC:d3dumddi.PFND3DDDI_SETDECODERENDERTARGET
title: PFND3DDDI_SETDECODERENDERTARGET
author: windows-driver-content
description: The SetDecodeRenderTarget function sets the render target surface for decoding operations.
old-location: display\setdecoderendertarget.htm
old-project: display
ms.assetid: d522b0f3-ca9c-4e79-96ad-ea9477858ef4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_SETDECODERENDERTARGET, SetDecodeRenderTarget, SetDecodeRenderTarget callback function [Display Devices], UserModeDisplayDriver_Functions_e5c55218-5663-4689-a696-6b9b1c0a7cce.xml, d3dumddi/SetDecodeRenderTarget, display.setdecoderendertarget
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
-	SetDecodeRenderTarget
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETDECODERENDERTARGET callback function
The <i>SetDecodeRenderTarget</i> function sets the render target surface for decoding operations.

## Syntax

```
PFND3DDDI_SETDECODERENDERTARGET Pfnd3dddiSetdecoderendertarget;

HRESULT Pfnd3dddiSetdecoderendertarget(
  HANDLE hDevice,
  CONST D3DDDIARG_SETDECODERENDERTARGET *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>SetDecodeRenderTarget</i> returns one of the following values:

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
The render target surface is successfully set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>SetDecodeRenderTarget</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>

## Remarks

The <i>SetDecodeRenderTarget</i> function can be called only outside of a <a href="https://msdn.microsoft.com/3e6153aa-7b21-429d-8908-1ff3a4d25e17">DecodeBeginFrame</a>/<a href="https://msdn.microsoft.com/6e8d3280-6ddc-4593-9208-c4f0c9ff254c">DecodeEndFrame</a> block. 

Decode render targets are always created atomically through calls to the <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function, where all of the decode buffers are indexes within a single resource. All decode render targets are created by setting the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544644">D3DDDI_RESOURCEFLAGS</a>.<b>DecodeRenderTarget</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543295">D3DDDIARG_SETDECODERENDERTARGET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544644">D3DDDI_RESOURCEFLAGS</a>



<a href="https://msdn.microsoft.com/3e6153aa-7b21-429d-8908-1ff3a4d25e17">DecodeBeginFrame</a>



<a href="https://msdn.microsoft.com/6e8d3280-6ddc-4593-9208-c4f0c9ff254c">DecodeEndFrame</a>