---
UID: NS:d3dumddi._D3DDDIARG_CREATEPIXELSHADER
title: "_D3DDDIARG_CREATEPIXELSHADER"
author: windows-driver-content
description: The D3DDDIARG_CREATEPIXELSHADER structure specifies a shader handle to associate with pixel shader code.
old-location: display\d3dddiarg_createpixelshader.htm
old-project: display
ms.assetid: dc7baff1-7e74-4666-805b-33b524c89c1d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_CREATEPIXELSHADER structure [Display Devices], display.d3dddiarg_createpixelshader, D3DDDIARG_CREATEPIXELSHADER, UMDisplayDriver_param_Structs_c1c78eaf-3eb9-4518-9b3c-f3fd5d6ce1f7.xml, _D3DDDIARG_CREATEPIXELSHADER, d3dumddi/D3DDDIARG_CREATEPIXELSHADER
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
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_CREATEPIXELSHADER
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEPIXELSHADER
---

# _D3DDDIARG_CREATEPIXELSHADER structure
The D3DDDIARG_CREATEPIXELSHADER structure specifies a shader handle to associate with pixel shader code.

## Syntax
````
typedef struct _D3DDDIARG_CREATEPIXELSHADER {
  UINT   CodeSize;
  HANDLE ShaderHandle;
} D3DDDIARG_CREATEPIXELSHADER;
````

## Members


`CodeSize`

[in] The size, in bytes, of the pixel shader code that is passed in the <i>pCode</i> parameter in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createpixelshader.md">CreatePixelShader</a> function.

`ShaderHandle`

[out] A handle to the pixel shader code.

## Remarks
For more information about programming shader assemblers, see <a href="https://msdn.microsoft.com/c858766c-b414-4971-b4d9-23ec94aca8ea">Processing Shader Codes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createpixelshader.md">CreatePixelShader</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATEPIXELSHADER structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>