---
UID: NF:wdbgexts.IsPtr64
title: IsPtr64 function
author: windows-driver-content
description: The IsPtr64 function determines if the target uses 64-bit pointers.
old-location: debugger\isptr64.htm
old-project: debugger
ms.assetid: 0474a8dc-e2e3-4c84-8058-6229bf0e9d62
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IsPtr64, debugger.isptr64, WdbgExts_Ref_488f3445-c3ae-4847-8e3b-cf3892dcd365.xml, IsPtr64 function [Windows Debugging], wdbgexts/IsPtr64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	IsPtr64
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---


# IsPtr64 function
The <b>IsPtr64</b> function determines if the target uses 64-bit pointers.

## Syntax

````
ULONG IsPtr64(void);
````

## Parameters

This function has no parameters.

## Return Value

The function returns <b>TRUE</b> if the target uses 64-bit pointers; <b>FALSE</b>, otherwise.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |
| **Library** | NtosKrnl.exe |