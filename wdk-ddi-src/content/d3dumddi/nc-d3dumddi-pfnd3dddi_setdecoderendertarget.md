---
UID: NC:d3dumddi.PFND3DDDI_SETDECODERENDERTARGET
title: PFND3DDDI_SETDECODERENDERTARGET
author: windows-driver-content
description: The SetDecodeRenderTarget function sets the render target surface for decoding operations.
old-location: display\setdecoderendertarget.htm
old-project: display
ms.assetid: d522b0f3-ca9c-4e79-96ad-ea9477858ef4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.setdecoderendertarget, SetDecodeRenderTarget callback function [Display Devices], SetDecodeRenderTarget, PFND3DDDI_SETDECODERENDERTARGET, PFND3DDDI_SETDECODERENDERTARGET, d3dumddi/SetDecodeRenderTarget, UserModeDisplayDriver_Functions_e5c55218-5663-4689-a696-6b9b1c0a7cce.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
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

The <i>SetDecodeRenderTarget</i> function can be called only outside of a <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a>/<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeendframe.md">DecodeEndFrame</a> block. 

Decode render targets are always created atomically through calls to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function, where all of the decode buffers are indexes within a single resource. All decode render targets are created by setting the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_resourceflags.md">D3DDDI_RESOURCEFLAGS</a>.<b>DecodeRenderTarget</b> bit-field flag in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeendframe.md">DecodeEndFrame</a>

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_resourceflags.md">D3DDDI_RESOURCEFLAGS</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setdecoderendertarget.md">D3DDDIARG_SETDECODERENDERTARGET</a>

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETDECODERENDERTARGET callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>