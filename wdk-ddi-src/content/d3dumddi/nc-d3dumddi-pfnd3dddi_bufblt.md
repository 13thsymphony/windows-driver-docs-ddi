---
UID: NC:d3dumddi.PFND3DDDI_BUFBLT
title: PFND3DDDI_BUFBLT
author: windows-driver-content
description: The BufBlt function performs a bit-block transfer (bitblt) operation from a source vertex or index buffer to a destination vertex or index buffer.
old-location: display\bufblt.htm
old-project: display
ms.assetid: d75f3fad-3bcd-44ad-9bd5-f61f5346cf8d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: BufBlt, BufBlt callback function [Display Devices], PFND3DDDI_BUFBLT, UserModeDisplayDriver_Functions_87f3469d-cae9-43e7-a0ae-d19bef34314e.xml, d3dumddi/BufBlt, display.bufblt
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
-	BufBlt
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_BUFBLT callback function
The <b>BufBlt</b> function performs a bit-block transfer (bitblt) operation from a source vertex or index buffer to a destination vertex or index buffer.

## Syntax

```
PFND3DDDI_BUFBLT Pfnd3dddiBufblt;

HRESULT Pfnd3dddiBufblt(
  HANDLE hDevice,
  CONST D3DDDIARG_BUFFERBLT *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<b>BufBlt</b> returns S_OK or an appropriate error result if the buffer bitblt operation is not successfully performed.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_bufferblt.md">D3DDDIARG_BUFFERBLT</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>