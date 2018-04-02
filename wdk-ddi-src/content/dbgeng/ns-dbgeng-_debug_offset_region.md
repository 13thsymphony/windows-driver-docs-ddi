---
UID: NS:dbgeng._DEBUG_OFFSET_REGION
title: "_DEBUG_OFFSET_REGION"
author: windows-driver-content
description: Defines a debug offset region.
old-location: debugger\debug_offset_region.htm
old-project: debugger
ms.assetid: 7116B31A-D584-4B9D-AFB4-5B15B659BE54
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PDEBUG_OFFSET_REGION, DEBUG_OFFSET_REGION, DEBUG_OFFSET_REGION structure [Windows Debugging], PDEBUG_OFFSET_REGION, PDEBUG_OFFSET_REGION structure pointer [Windows Debugging], _DEBUG_OFFSET_REGION, dbgeng/DEBUG_OFFSET_REGION, dbgeng/PDEBUG_OFFSET_REGION, debugger.debug_offset_region"
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
-	DEBUG_OFFSET_REGION
product: Windows
targetos: Windows
req.typenames: DEBUG_OFFSET_REGION, *PDEBUG_OFFSET_REGION
---

# _DEBUG_OFFSET_REGION structure
Defines a debug offset region.

## Syntax
```
typedef struct _DEBUG_OFFSET_REGION {
  ULONG64 Base;
  ULONG64 Size;
} *PDEBUG_OFFSET_REGION, DEBUG_OFFSET_REGION;
```

## Members


`Base`

The base value of the offset region.

`Size`

The size of the region.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dbgeng.h (include DbgEng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549798">IDebugAdvanced</a>