---
UID: NS:dbgeng._DEBUG_SYMBOL_SOURCE_ENTRY
title: "_DEBUG_SYMBOL_SOURCE_ENTRY"
author: windows-driver-content
description: The DEBUG_SYMBOL_SOURCE_ENTRY structure describes a section of the source code and a corresponding region of the target's memory.
old-location: debugger\debug_symbol_source_entry.htm
old-project: debugger
ms.assetid: 595d5a90-6ec8-4841-a38b-c0cbf26ed082
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: DEBUG_SYMBOL_SOURCE_ENTRY, _DEBUG_SYMBOL_SOURCE_ENTRY, dbgeng/PDEBUG_SYMBOL_SOURCE_ENTRY, dbgeng/DEBUG_SYMBOL_SOURCE_ENTRY, PDEBUG_SYMBOL_SOURCE_ENTRY structure pointer [Windows Debugging], DEBUG_SYMBOL_SOURCE_ENTRY structure [Windows Debugging], PDEBUG_SYMBOL_SOURCE_ENTRY, debugger.debug_symbol_source_entry, *PDEBUG_SYMBOL_SOURCE_ENTRY, Structures_9f8ab4b6-98b2-4a10-a450-bb73e655dd32.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	DbgEng.h
apiname:
-	DEBUG_SYMBOL_SOURCE_ENTRY
product: Windows
targetos: Windows
req.typenames: "*PDEBUG_SYMBOL_SOURCE_ENTRY, DEBUG_SYMBOL_SOURCE_ENTRY"
---

# _DEBUG_SYMBOL_SOURCE_ENTRY structure
The DEBUG_SYMBOL_SOURCE_ENTRY structure describes a section of the source code and a corresponding region of the target's memory.

## Syntax
````
typedef struct _DEBUG_SYMBOL_SOURCE_ENTRY {
  ULONG64 ModuleBase;
  ULONG64 Offset;
  ULONG64 FileNameId;
  ULONG64 EngineInternal;
  ULONG   Size;
  ULONG   Flags;
  ULONG   FileNameSize;
  ULONG   StartLine;
  ULONG   EndLine;
  ULONG   StartColumn;
  ULONG   EndColumn;
  ULONG   Reserved;
} DEBUG_SYMBOL_SOURCE_ENTRY, *PDEBUG_SYMBOL_SOURCE_ENTRY;
````

## Members


`EndColumn`

The column number of the end of the region of source code. The number of the first column is one. If this information is not available, <b>StartLine</b> is set to DEBUG_ANY_ID.

`EndLine`

The line number of the end of the region of source code in the file. The number of the first line in the file is one. If this information is not available, <b>StartLine</b> is set to DEBUG_ANY_ID.

`EngineInternal`

Reserved for internal debugger engine use.

`FileNameId`

Identifier for the source code file name. If this information is not available, <b>FieldNameId</b> is set to zero.

`FileNameSize`

The number of characters in the source filename, including the terminator.

`Flags`

Set to zero.

`ModuleBase`

The base address, in the target's virtual address space, of the module that the source symbol came from.

`Offset`

The location of the memory corresponding to the source code in the target's virtual address space.

`Reserved`

Reserved for future use.

`Size`

The size of the region of memory corresponding to the source code. If this information is not available, <b>Size</b> is set to one.

`StartColumn`

The column number of the start of the region of source code. The number of the first column is one. If this information is not available, <b>StartLine</b> is set to DEBUG_ANY_ID.

`StartLine`

The line number of the start of the region of source code in the file. The number of the first line in the file is one. If this information is not available, <b>StartLine</b> is set to DEBUG_ANY_ID.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dbgeng.h (include DbgEng.h) |