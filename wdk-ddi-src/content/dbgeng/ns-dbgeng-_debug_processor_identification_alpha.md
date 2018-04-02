---
UID: NS:dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_ALPHA
title: "_DEBUG_PROCESSOR_IDENTIFICATION_ALPHA"
author: windows-driver-content
description: Identifies an Alpha processor.
old-location: debugger\debug_processor_identification_alpha.htm
old-project: debugger
ms.assetid: AE0DB2CC-6364-4B50-8CD3-8EF8B495FBED
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA, DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, DEBUG_PROCESSOR_IDENTIFICATION_ALPHA structure [Windows Debugging], PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA, PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA structure pointer [Windows Debugging], _DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, dbgeng/DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, dbgeng/PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA, debugger.debug_processor_identification_alpha"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	DbgEng.h
api_name:
-	DEBUG_PROCESSOR_IDENTIFICATION_ALPHA
product:
- Windows
targetos: Windows
req.typenames: DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, *PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA
---

# _DEBUG_PROCESSOR_IDENTIFICATION_ALPHA structure
Identifies an Alpha processor.

## Syntax
```
typedef struct _DEBUG_PROCESSOR_IDENTIFICATION_ALPHA {
  ULONG Type;
  ULONG Revision;
} DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, *PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA;
```

## Members


`Type`

The type of the processor.

`Revision`

The revision of the processor.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dbgeng.h (include DbgEng.h) |

## See Also

<a href="https://msdn.microsoft.com/2C4C03BC-0D84-4151-B1A1-FE76F0355CD6">DEBUG_PROCESSOR_IDENTIFICATION_ALL</a>