---
UID: NC:d3dumddi.PFND3DDDI_DRAWINDEXEDPRIMITIVE
title: PFND3DDDI_DRAWINDEXEDPRIMITIVE
author: windows-driver-content
description: The DrawIndexedPrimitive function draws indexed primitives that the Microsoft Direct3D runtime has not transformed the index data in.
old-location: display\drawindexedprimitive.htm
old-project: display
ms.assetid: 12bb6274-d042-43bb-b9f5-1417f42da729
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.drawindexedprimitive, DrawIndexedPrimitive callback function [Display Devices], DrawIndexedPrimitive, PFND3DDDI_DRAWINDEXEDPRIMITIVE, PFND3DDDI_DRAWINDEXEDPRIMITIVE, d3dumddi/DrawIndexedPrimitive, UserModeDisplayDriver_Functions_427fa7b5-5b52-4314-b097-aea6d27cb535.xml
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
-	DrawIndexedPrimitive
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DRAWINDEXEDPRIMITIVE callback function
The <b>DrawIndexedPrimitive</b> function draws indexed primitives that the Microsoft Direct3D runtime has not transformed the index data in.

## Syntax

```
PFND3DDDI_DRAWINDEXEDPRIMITIVE Pfnd3dddiDrawindexedprimitive;

HRESULT Pfnd3dddiDrawindexedprimitive(
  HANDLE hDevice,
  CONST D3DDDIARG_DRAWINDEXEDPRIMITIVE *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<b>DrawIndexedPrimitive</b> returns S_OK or an appropriate error result if the indexed primitive is not successfully drawn.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawindexedprimitive2.md">DrawIndexedPrimitive2</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawindexedprimitive.md">D3DDDIARG_DRAWINDEXEDPRIMITIVE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DRAWINDEXEDPRIMITIVE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>