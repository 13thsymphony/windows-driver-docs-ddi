---
UID: NC:d3dumddi.PFND3DDDI_MULTIPLYTRANSFORM
title: PFND3DDDI_MULTIPLYTRANSFORM
author: windows-driver-content
description: The MultiplyTransform function modifies the current transform.
old-location: display\multiplytransform.htm
old-project: display
ms.assetid: 69d94062-5655-4d49-a116-7fa7e2b51a91
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: MultiplyTransform, MultiplyTransform callback function [Display Devices], PFND3DDDI_MULTIPLYTRANSFORM, UserModeDisplayDriver_Functions_4058eef2-8ccd-46e2-ad8d-fd0905811651.xml, d3dumddi/MultiplyTransform, display.multiplytransform
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
-	MultiplyTransform
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_MULTIPLYTRANSFORM callback function
The <i>MultiplyTransform</i> function modifies the current transform.

## Syntax

```
PFND3DDDI_MULTIPLYTRANSFORM Pfnd3dddiMultiplytransform;

HRESULT Pfnd3dddiMultiplytransform(
  HANDLE hDevice,
  CONST D3DDDIARG_MULTIPLYTRANSFORM *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>MultiplyTransform</i> returns S_OK or an appropriate error result if the transform is not successfully modified.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543221">D3DDDIARG_MULTIPLYTRANSFORM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>