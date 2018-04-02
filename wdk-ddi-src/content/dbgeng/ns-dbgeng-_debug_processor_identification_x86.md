---
UID: NS:dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_X86
title: "_DEBUG_PROCESSOR_IDENTIFICATION_X86"
author: windows-driver-content
description: Identifies an x86 processor.
old-location: debugger\debug_processor_identification_x86.htm
old-project: debugger
ms.assetid: B5AD9CE8-B0F0-49BC-984E-4372FD3BF93B
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PDEBUG_PROCESSOR_IDENTIFICATION_X86, DEBUG_PROCESSOR_IDENTIFICATION_X86, DEBUG_PROCESSOR_IDENTIFICATION_X86 structure [Windows Debugging], PDEBUG_PROCESSOR_IDENTIFICATION_X86, PDEBUG_PROCESSOR_IDENTIFICATION_X86 structure pointer [Windows Debugging], _DEBUG_PROCESSOR_IDENTIFICATION_X86, dbgeng/DEBUG_PROCESSOR_IDENTIFICATION_X86, dbgeng/PDEBUG_PROCESSOR_IDENTIFICATION_X86, debugger.debug_processor_identification_x86"
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
-	DEBUG_PROCESSOR_IDENTIFICATION_X86
product: Windows
targetos: Windows
req.typenames: DEBUG_PROCESSOR_IDENTIFICATION_X86, *PDEBUG_PROCESSOR_IDENTIFICATION_X86
---

# _DEBUG_PROCESSOR_IDENTIFICATION_X86 structure
Identifies an x86 processor.

## Syntax
```
typedef struct _DEBUG_PROCESSOR_IDENTIFICATION_X86 {
  ULONG Family;
  ULONG Model;
  ULONG Stepping;
  CHAR  VendorString[16];
} *PDEBUG_PROCESSOR_IDENTIFICATION_X86, DEBUG_PROCESSOR_IDENTIFICATION_X86;
```

## Members


`Family`

The family of the processor.

`Model`

The model of the processor.

`Stepping`

The stepping value of the processor.

`VendorString`

A vendor specified string.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dbgeng.h (include DbgEng.h) |

## See Also

<a href="https://msdn.microsoft.com/2C4C03BC-0D84-4151-B1A1-FE76F0355CD6">DEBUG_PROCESSOR_IDENTIFICATION_ALL</a>