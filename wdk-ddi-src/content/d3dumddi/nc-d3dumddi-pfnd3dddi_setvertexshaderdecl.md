---
UID: NC:d3dumddi.PFND3DDDI_SETVERTEXSHADERDECL
title: PFND3DDDI_SETVERTEXSHADERDECL
author: windows-driver-content
description: The SetVertexShaderDecl function sets the vertex shader declaration so that all of the subsequent drawing operations use that declaration.
old-location: display\setvertexshaderdecl.htm
old-project: display
ms.assetid: 6387d632-78e2-4594-a58a-b11b2e831cc0
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.setvertexshaderdecl, SetVertexShaderDecl callback function [Display Devices], SetVertexShaderDecl, PFND3DDDI_SETVERTEXSHADERDECL, PFND3DDDI_SETVERTEXSHADERDECL, d3dumddi/SetVertexShaderDecl, UserModeDisplayDriver_Functions_83e6bdef-65e0-4357-aa4c-51e20cbeb6d5.xml
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
-	SetVertexShaderDecl
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETVERTEXSHADERDECL callback function
The <i>SetVertexShaderDecl</i> function sets the vertex shader declaration so that all of the subsequent drawing operations use that declaration.

## Syntax

```
PFND3DDDI_SETVERTEXSHADERDECL Pfnd3dddiSetvertexshaderdecl;

HRESULT Pfnd3dddiSetvertexshaderdecl(
  HANDLE hDevice,
   HANDLE
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`HANDLE`




## Return Value

<i>SetVertexShaderDecl</i> returns S_OK or an appropriate error result if the vertex shader declaration is not successfully set.

## Remarks

After setting the vertex shader declaration, all of the drawing operations use that declaration until another declaration is selected.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETVERTEXSHADERDECL callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>