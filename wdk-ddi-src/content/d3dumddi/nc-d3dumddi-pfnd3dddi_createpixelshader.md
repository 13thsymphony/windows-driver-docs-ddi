---
UID: NC.d3dumddi.PFND3DDDI_CREATEPIXELSHADER
title: PFND3DDDI_CREATEPIXELSHADER
author: windows-driver-content
description: The CreatePixelShader function converts pixel shader code into a hardware-specific format and associates this code with a shader handle.
old-location: display\createpixelshader.htm
old-project: display
ms.assetid: b80a1823-6d91-440f-89e4-f7248579cc8f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
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
req.alt-api: CreatePixelShader
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

# PFND3DDDI_CREATEPIXELSHADER callback



## -description
The <b>CreatePixelShader</b> function converts pixel shader code into a hardware-specific format and associates this code with a shader handle.


## -prototype

````
PFND3DDDI_CREATEPIXELSHADER CreatePixelShader;

__checkReturn HRESULT APIENTRY CreatePixelShader(
  _In_          HANDLE                      hDevice,
  _Inout_       D3DDDIARG_CREATEPIXELSHADER *pData,
  _In_    const UINT                        *pCode
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).

### -param pData [in, out]

 A pointer to a <a href="display.d3dddiarg_createpixelshader">D3DDDIARG_CREATEPIXELSHADER</a> structure that retrieves the shader handle that is associated with the pixel shader code that is specified by <b>pCode</b>.

### -param pCode [in]

 An array of CONST UINT tokens that make up the pixel shader code.

## -returns
<b>CreatePixelShader</b> returns S_OK or an appropriate error result if the pixel shader code object is not successfully created.

## -remarks
For more information about programming shader assemblers, see <a href="https://msdn.microsoft.com/c858766c-b414-4971-b4d9-23ec94aca8ea">Processing Shader Codes</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<a href="display.d3dddiarg_createpixelshader">D3DDDIARG_CREATEPIXELSHADER</a>
</dt>
<dt>
<a href="display.d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CREATEPIXELSHADER callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
