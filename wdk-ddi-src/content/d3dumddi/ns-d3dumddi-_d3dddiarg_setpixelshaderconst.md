---
UID: NS.D3DUMDDI._D3DDDIARG_SETPIXELSHADERCONST
title: _D3DDDIARG_SETPIXELSHADERCONST
author: windows-driver-content
description: The D3DDDIARG_SETPIXELSHADERCONST structure describes how to set the pixel shader constant registers.
old-location: display\d3dddiarg_setpixelshaderconst.htm
old-project: display
ms.assetid: 1c8cbbdc-ac2e-462e-9d5c-484305a41302
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDIARG_SETPIXELSHADERCONST, D3DDDIARG_SETPIXELSHADERCONST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_SETPIXELSHADERCONST
req.alt-loc: d3dumddi.h
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
---

# _D3DDDIARG_SETPIXELSHADERCONST structure



## -description
The D3DDDIARG_SETPIXELSHADERCONST structure describes how to set the pixel shader constant registers. 


## -syntax

````
typedef struct _D3DDDIARG_SETPIXELSHADERCONST {
  UINT Register;
  UINT Count;
} D3DDDIARG_SETPIXELSHADERCONST;
````


## -struct-fields

### -field Register

[in] The index of the first pixel shader constant register whose value is set.

### -field Count

[in] The number of constant registers to set and, therefore, the number of values in the array that is passed in the <i>pRegisters</i> parameter in the call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconst.md">SetPixelShaderConst</a>, <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconsti.md">SetPixelShaderConstI</a>, or <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconstb.md">SetPixelShaderConstB</a> function.

## -remarks
The <b>Count</b> member specifies the following values, depending on the structure type that is used in the call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconst.md">SetPixelShaderConst</a>, <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconsti.md">SetPixelShaderConstI</a>, or <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconstb.md">SetPixelShaderConstB</a> function: 

Four-element, single-precision float vectors for the D3DDDIARG_SETPIXELSHADERCONST structure in the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconst.md">SetPixelShaderConst</a> call.

Four-integer vectors for the D3DDDIARG_SETPIXELSHADERCONSTI structure in the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconsti.md">SetPixelShaderConstI</a> call.

Boolean values for the D3DDDIARG_SETPIXELSHADERCONSTB structure in the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconstb.md">SetPixelShaderConstB</a> call.

The preceding structures are identical, as the following definitions show:

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconst.md">SetPixelShaderConst</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconstb.md">SetPixelShaderConstB</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconsti.md">SetPixelShaderConstI</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETPIXELSHADERCONST structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
