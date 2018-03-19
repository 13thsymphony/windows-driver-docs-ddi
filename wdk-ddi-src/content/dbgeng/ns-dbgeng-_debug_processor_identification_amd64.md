---
UID: NS:dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_AMD64
title: "_DEBUG_PROCESSOR_IDENTIFICATION_AMD64"
author: windows-driver-content
description: Identifies an AMD64 processor.
old-location: debugger\debug_processor_identification_amd64.htm
old-project: debugger
ms.assetid: 71E28D54-19D2-4A62-9A63-633186F67AD5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PDEBUG_PROCESSOR_IDENTIFICATION_AMD64, DEBUG_PROCESSOR_IDENTIFICATION_AMD64, DEBUG_PROCESSOR_IDENTIFICATION_AMD64 structure [Windows Debugging], PDEBUG_PROCESSOR_IDENTIFICATION_AMD64, PDEBUG_PROCESSOR_IDENTIFICATION_AMD64 structure pointer [Windows Debugging], _DEBUG_PROCESSOR_IDENTIFICATION_AMD64, dbgeng/DEBUG_PROCESSOR_IDENTIFICATION_AMD64, dbgeng/PDEBUG_PROCESSOR_IDENTIFICATION_AMD64, debugger.debug_processor_identification_amd64"
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
-	DEBUG_PROCESSOR_IDENTIFICATION_AMD64
product: Windows
targetos: Windows
req.typenames: DEBUG_PROCESSOR_IDENTIFICATION_AMD64, *PDEBUG_PROCESSOR_IDENTIFICATION_AMD64
---

# _DEBUG_PROCESSOR_IDENTIFICATION_AMD64 structure
Identifies an AMD64 processor.

## Syntax
````
typedef struct _DEBUG_PROCESSOR_IDENTIFICATION_AMD64 {
  ULONG Family;
  ULONG Model;
  ULONG Stepping;
  CHAR  VendorString[16];
} DEBUG_PROCESSOR_IDENTIFICATION_AMD64, *PDEBUG_PROCESSOR_IDENTIFICATION_AMD64;
````

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

<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_all.md">DEBUG_PROCESSOR_IDENTIFICATION_ALL</a>