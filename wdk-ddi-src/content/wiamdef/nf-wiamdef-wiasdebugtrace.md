---
UID: NF:wiamdef.wiasDebugTrace
title: wiasDebugTrace function
author: windows-driver-content
description: This function prints a debug trace string in the Device Manager debug console.
old-location: image\wiasdebugtrace.htm
old-project: image
ms.assetid: db39c7f6-d966-4538-8ee9-d3623995535c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiasdebugtrace, wiamdef/wiasDebugTrace, wiasDebugTrace, wiasDebugTrace function [Imaging Devices], wiasFncs_b6582555-3674-4261-a542-9a6388649bb0.xml
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
-	wiasDebugTrace
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasDebugTrace function
This function prints a debug trace string in the Device Manager debug console.

## Syntax

```
void wiasDebugTrace(
  HINSTANCE hInstance,
  LPCSTR    pszFormat,
  ...       
);
```

## Parameters

`hInstance`

Is the module handle of calling module.

`pszFormat`

TBD

`Arg1`




## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## Remarks

The wiasDebugTrace function is not recommended for Windows XP and later. For Windows XP use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549600">WIAS_LTRACE</a> macro instead. For Windows Vista use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549619">WIAS_TRACE</a> macro instead.

To enable tracing in free builds, drivers must define the WIAS_DEBUG macro. Tracing is enabled by default in checked and debug builds of the operating system.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** | Wiaservc.lib |
| **DLL** | Wiaservc.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549600">WIAS_LTRACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549619">WIAS_TRACE</a>