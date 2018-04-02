---
UID: NF:wiamdef.wiasWritePropFloat
title: wiasWritePropFloat function
author: windows-driver-content
description: The wiasWritePropFloat function writes a single floating-point property value to a WIA item.
old-location: image\wiaswritepropfloat.htm
old-project: image
ms.assetid: 097cd455-018e-46ef-8b8f-8eae7ea3eaff
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiaswritepropfloat, wiamdef/wiasWritePropFloat, wiasFncs_49539474-675e-420d-b7a4-67f147017975.xml, wiasWritePropFloat, wiasWritePropFloat function [Imaging Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Wiaservc.dll
api_name:
-	wiasWritePropFloat
product:
- Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasWritePropFloat function
The <b>wiasWritePropFloat </b>function writes a single floating-point property value to a WIA item.

## Syntax

```
HRESULT wiasWritePropFloat(
  BYTE   *pWiasContext,
  PROPID propid,
  float  fVal
);
```

## Parameters

`pWiasContext`

A Pointer to a WIA item context.

`propid`

Specifies the property identifier.

`fVal`

Specifies the floating-point property value to write to the item.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** | Wiaservc.lib |
| **DLL** | Wiaservc.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549320">wiasReadPropFloat</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549500">wiasWritePropBin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549512">wiasWritePropGuid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549515">wiasWritePropLong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549525">wiasWritePropStr</a>