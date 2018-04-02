---
UID: NF:wiamdef.wiasReadPropBin
title: wiasReadPropBin function
author: windows-driver-content
description: The wiasReadPropBin function retrieves a binary-data property value from a WIA item.
old-location: image\wiasreadpropbin.htm
old-project: image
ms.assetid: f62b63e3-011b-43ef-b7f5-769aa00ff3ca
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiasreadpropbin, wiamdef/wiasReadPropBin, wiasFncs_484baa0a-a423-4f4d-a33c-d155a8f4974c.xml, wiasReadPropBin, wiasReadPropBin function [Imaging Devices]
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
-	wiasReadPropBin
product:
- Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasReadPropBin function
The <b>wiasReadPropBin</b> function retrieves a binary-data property value from a WIA item.

## Syntax

```
HRESULT wiasReadPropBin(
  BYTE   *pWiasContext,
  PROPID propid,
  BYTE   **ppbVal,
  BYTE   **ppbValOld,
  BOOL   bMustExist
);
```

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`propid`

Specifies the property identifier.

`ppbVal`

Pointer to a memory location that receives the address of a buffer allocated by this function. Upon return, the buffer contains the property's binary data.

`ppbValOld`

Pointer to a memory location that receives the address of a buffer allocated by the minidriver. Upon return, the buffer contains the previous value of the property's binary data. If this information is not needed, this parameter can be set to <b>NULL</b>.

`bMustExist`

Indicates whether the property must exist. If set to <b>TRUE</b>, the property must exist; if set to <b>FALSE</b>, the property does not have to exist.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## Remarks

This function allocates a buffer and stores its address in the <i>ppbVal</i> parameter. The minidriver must free the buffer by calling <b>CoTaskMemFree</b> (described in the Windows SDK documentation).

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549325">wiasReadPropGuid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549330">wiasReadPropLong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549341">wiasReadPropStr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549500">wiasWritePropBin</a>