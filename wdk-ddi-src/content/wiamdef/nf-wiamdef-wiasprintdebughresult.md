---
UID: NF:wiamdef.wiasPrintDebugHResult
title: wiasPrintDebugHResult function
author: windows-driver-content
description: The wiasPrintDebugHResult function is obsolete for Windows XP and later, and is no longer supported. Use the WIAS_LHRESULT macro instead.This function prints an HRESULT string on the Device Manager debug console.
old-location: image\wiasprintdebughresult.htm
old-project: image
ms.assetid: f9dc5379-0efa-4743-9460-bfb16945768b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiasprintdebughresult, wiamdef/wiasPrintDebugHResult, wiasFncs_932e688a-da37-4a53-91ff-f0c0abca4f98.xml, wiasPrintDebugHResult, wiasPrintDebugHResult function [Imaging Devices]
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
-	wiasPrintDebugHResult
product:
- Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasPrintDebugHResult function
The <b>wiasPrintDebugHResult</b> function is <b>obsolete</b> for Windows XP and later, and is no longer supported. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549589">WIAS_LHRESULT</a> macro instead.

This function prints an HRESULT string on the Device Manager debug console.

## Syntax

```
void wiasPrintDebugHResult(
  HINSTANCE hInstance,
  HRESULT   hr
);
```

## Parameters

`hInstance`

Is the module handle of the calling module.

`hr`

Specifies the HRESULT to be printed.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549589">WIAS_LHRESULT</a>