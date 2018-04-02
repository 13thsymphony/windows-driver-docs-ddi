---
UID: NC:d3dumddi.PFND3DDDI_FLIPOVERLAY
title: PFND3DDDI_FLIPOVERLAY
author: windows-driver-content
description: The FlipOverlay function causes the overlay hardware to start displaying the given new allocation.
old-location: display\flipoverlay.htm
old-project: display
ms.assetid: 8490ebdd-f993-4c77-b6da-d57ef5e5d05f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FlipOverlay, FlipOverlay callback function [Display Devices], PFND3DDDI_FLIPOVERLAY, UserModeDisplayDriver_Functions_4a2c5f7b-8d52-465f-84ea-a1fc4f53381b.xml, d3dumddi/FlipOverlay, display.flipoverlay
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
-	FlipOverlay
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_FLIPOVERLAY callback function
The <i>FlipOverlay</i> function causes the overlay hardware to start displaying the given new allocation.

## Syntax

```
PFND3DDDI_FLIPOVERLAY Pfnd3dddiFlipoverlay;

HRESULT Pfnd3dddiFlipoverlay(
  HANDLE hDevice,
  CONST D3DDDIARG_FLIPOVERLAY *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>FlipOverlay</i> returns S_OK or an appropriate error result if the new allocation is not successfully displayed.

## Remarks

Overlays are independent from the resources that are displayed by using the overlays.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543124">D3DDDIARG_FLIPOVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>