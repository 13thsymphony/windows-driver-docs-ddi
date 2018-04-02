---
UID: NC:d3dumddi.PFND3DDDI_SETLIGHT
title: PFND3DDDI_SETLIGHT
author: windows-driver-content
description: The SetLight function sets properties for a light source.
old-location: display\setlight.htm
old-project: display
ms.assetid: 28e3992e-a636-47e2-a5a6-5da06d276b5c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_SETLIGHT, SetLight, SetLight callback function [Display Devices], UserModeDisplayDriver_Functions_82c42629-2344-4778-aaf4-e41acac4cfce.xml, d3dumddi/SetLight, display.setlight
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
-	SetLight
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETLIGHT callback function
The <i>SetLight</i> function sets properties for a light source.

## Syntax

```
PFND3DDDI_SETLIGHT Pfnd3dddiSetlight;

HRESULT Pfnd3dddiSetlight(
  HANDLE hDevice,
  CONST D3DDDIARG_SETLIGHT *,
  CONST D3DDDI_LIGHT *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`



`*`




## Return Value

<i>SetLight</i> returns S_OK or an appropriate error result if the light properties are not successfully set.

## Remarks

Light properties describe the type and color of a light source. Depending on the type of light that is being used, a light can have properties for attenuation and range or for spotlight effects. However, not all types of lights will use all of the properties. For more information about light properties, see the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543317">D3DDDIARG_SETLIGHT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544579">D3DDDI_LIGHT</a>