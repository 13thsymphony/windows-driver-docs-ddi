---
UID: NC:d3dumddi.PFND3DDDI_SETINDICES
title: PFND3DDDI_SETINDICES
author: windows-driver-content
description: The SetIndices function sets the current index buffer.
old-location: display\setindices.htm
old-project: display
ms.assetid: 5348b3f9-78c5-4915-ba68-296d6f9f916c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_SETINDICES, SetIndices, SetIndices callback function [Display Devices], UserModeDisplayDriver_Functions_c51c5796-e271-4b76-a013-88038767d356.xml, d3dumddi/SetIndices, display.setindices
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
-	SetIndices
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETINDICES callback function
The <i>SetIndices</i> function sets the current index buffer.

## Syntax

```
PFND3DDDI_SETINDICES Pfnd3dddiSetindices;

HRESULT Pfnd3dddiSetindices(
  HANDLE hDevice,
  CONST D3DDDIARG_SETINDICES *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>SetIndices</i> returns S_OK or an appropriate error result if the index buffer is not successfully set.

## Remarks

The Microsoft Direct3D runtime supplies a handle value of zero in the <b>hIndexBuffer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543313">D3DDDIARG_SETINDICES</a> structure that is pointed to by the <i>pData</i> parameter to clear the current index buffer. The driver should handle subsequent attempts to draw indexed primitives (before a new current index buffer is established) so that a crash does not occur. The debug version of your driver should display informative messages to the debug output stream when this error condition is detected.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543313">D3DDDIARG_SETINDICES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>