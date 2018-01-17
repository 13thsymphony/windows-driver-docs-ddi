---
UID: NC:d3dumddi.PFND3DDDI_SETPIXELSHADERCONSTI
title: PFND3DDDI_SETPIXELSHADERCONSTI
author: windows-driver-content
description: The SetPixelShaderConstI function sets one or more pixel shader constant registers with integer values.
old-location: display\setpixelshaderconsti.htm
old-project: display
ms.assetid: fafc046e-0595-4901-bfb1-70bd980388bc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
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
req.alt-api: SetPixelShaderConstI
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
req.typenames: *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
---

# PFND3DDDI_SETPIXELSHADERCONSTI callback



## -description
The <i>SetPixelShaderConstI</i> function sets one or more pixel shader constant registers with integer values. 



## -prototype

````
PFND3DDDI_SETPIXELSHADERCONSTI SetPixelShaderConstI;

__checkReturn HRESULT APIENTRY SetPixelShaderConstI(
  _In_       HANDLE                        hDevice,
  _In_ const D3DDDIARG_SETPIXELSHADERCONST *pData,
  _In_ const INT                           *pRegisters
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setpixelshaderconst.md">D3DDDIARG_SETPIXELSHADERCONST</a> structure that describes how to set the pixel shader constant registers.


### -param pRegisters [in]

 A pointer to a buffer that contains INT values to copy.


## -returns
<i>SetPixelShaderConstI</i> returns S_OK or an appropriate error result if the pixel shader constant registers are not successfully set with integer values.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setpixelshaderconst.md">D3DDDIARG_SETPIXELSHADERCONST</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETPIXELSHADERCONSTI callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

