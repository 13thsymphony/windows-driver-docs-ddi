---
UID: NF:wiamdef.wiasReadPropStr
title: wiasReadPropStr function
author: windows-driver-content
description: The wiasReadPropStr function retrieves a string property value from a WIA item.
old-location: image\wiasreadpropstr.htm
old-project: image
ms.assetid: b072b4ec-790f-454b-b94a-bfe44674f600
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiasreadpropstr, wiamdef/wiasReadPropStr, wiasFncs_b0756dcf-44dd-4a9f-ad9a-1edff1b8e6f6.xml, wiasReadPropStr, wiasReadPropStr function [Imaging Devices]
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
-	wiasReadPropStr
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasReadPropStr function
The <b>wiasReadPropStr</b> function retrieves a string property value from a WIA item.

## Syntax

````
HRESULT _stdcall wiasReadPropStr(
  _In_      BYTE   *pWiasContext,
            PROPID propid,
  _Out_     BSTR   *pbstr,
  _Out_opt_ BSTR   *pbstrOld,
            BOOL   bMustExist
);
````

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`propid`

Specifies the property identifier.

`pbstr`

Pointer to a memory location that receives the first byte of the property's string value.

`pbstrOld`

Pointer to a memory location that receives the first byte of the property's previous value. If this information is not needed, set this parameter to <b>NULL</b>.

`bMustExist`

Indicates whether the property must exist. If set to <b>TRUE</b>, the property must exist; if set to <b>FALSE</b>, the property does not have to exist.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## Remarks

When the minidriver has completed using the string it received from this function, it must deallocate the memory used for the string.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** | Wiaservc.lib |
| **DLL** | Wiaservc.dll |

## See Also

<a href="..\wiamdef\nf-wiamdef-wiaswritepropstr.md">wiasWritePropStr</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadpropguid.md">wiasReadPropGuid</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadpropfloat.md">wiasReadPropFloat</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadpropbin.md">wiasReadPropBin</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadproplong.md">wiasReadPropLong</a>