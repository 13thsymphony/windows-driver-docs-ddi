---
UID: NF:wiamdef.wiasDebugError
title: wiasDebugError function
author: windows-driver-content
description: This function prints a debug error string in the Device Manager debug console. The output color is always red.
old-location: image\wiasdebugerror.htm
old-project: image
ms.assetid: fcddc83d-5fb1-43ad-9abd-8d5e2549b580
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiasdebugerror, wiamdef/wiasDebugError, wiasDebugError, wiasDebugError function [Imaging Devices], wiasFncs_0ccba388-a6ca-42b9-acd5-720b6763a202.xml
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
-	wiasDebugError
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasDebugError function
This function prints a debug error string in the Device Manager debug console. The output color is always red.

## Syntax

````
VOID __cdecl wiasDebugError(
   HINSTANCE   hInstance,
   LPCSTR      pszFormat, ...
);
````

## Parameters

`hInstance`

Is the module handle of calling module.

`pszFormat`

TBD

`Arg1`




## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## Remarks

The wiasDebugError function is not recommended for Windows XP and later. For Windows XP use the <a href="..\wiautil\nf-wiautil-wias_lerror.md">WIAS_LERROR</a> macro instead. For Windows Vista use the <a href="..\wiautil\nf-wiautil-wias_error.md">WIAS_ERROR</a> macro instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** | Wiaservc.lib |
| **DLL** | Wiaservc.dll |

## See Also

<a href="..\wiautil\nf-wiautil-wias_lerror.md">WIAS_LERROR</a>



<a href="..\wiautil\nf-wiautil-wias_error.md">WIAS_ERROR</a>