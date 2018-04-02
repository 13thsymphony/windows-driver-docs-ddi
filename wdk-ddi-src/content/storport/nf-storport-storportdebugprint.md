---
UID: NF:storport.StorPortDebugPrint
title: StorPortDebugPrint function
author: windows-driver-content
description: The StorPortDebugPrint routine prints a debug string to the kernel debugger, if the debugger is attached.
old-location: storage\storportdebugprint.htm
old-project: storage
ms.assetid: 46845a10-c44b-4d11-b82e-986bfc066b97
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortDebugPrint, StorPortDebugPrint routine [Storage Devices], storage.storportdebugprint, storport/StorPortDebugPrint, storprt_4c594dd0-20a0-456f-acdb-3c08198dc8b5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortDebugPrint
product:
- Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortDebugPrint function
The <b>StorPortDebugPrint</b> routine prints a debug string to the kernel debugger, if the debugger is attached.

## Syntax

```
STORPORT_API VOID StorPortDebugPrint(
  ULONG DebugPrintLevel,
  PSTR  DebugMessage,
  ...   
);
```

## Parameters

`DebugPrintLevel`

Indicates the amount of debug information that will be displayed.

`DebugMessage`

Pointer to the debug message to be printed.

`Arg1`




## Return Value

None

## Remarks

To see these debug strings, the driver writer must set nt!Kd_STORMINIPORT_Mask. This follows the new system-wide debug print mechanism.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |