---
UID: NC:d3dumddi.PFND3DDDI_SETRENDERTARGET
title: PFND3DDDI_SETRENDERTARGET
author: windows-driver-content
description: The SetRenderTarget function sets the render target surface.
old-location: display\setrendertarget.htm
old-project: display
ms.assetid: 067378bd-a2d8-4c83-9436-531519eadaa3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETRENDERTARGET, SetRenderTarget, SetRenderTarget callback function [Display Devices], UserModeDisplayDriver_Functions_c6c2e714-ac5c-4106-98da-1d87a322c652.xml, d3dumddi/SetRenderTarget, display.setrendertarget
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
-	SetRenderTarget
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETRENDERTARGET callback function
The <i>SetRenderTarget</i> function sets the render target surface.

## Syntax

```
PFND3DDDI_SETRENDERTARGET Pfnd3dddiSetrendertarget;

HRESULT Pfnd3dddiSetrendertarget(
  HANDLE hDevice,
  CONST D3DDDIARG_SETRENDERTARGET *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>SetRenderTarget</i> returns S_OK or an appropriate error result if the render target surface is not successfully set.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setrendertarget.md">D3DDDIARG_SETRENDERTARGET</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETRENDERTARGET callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>