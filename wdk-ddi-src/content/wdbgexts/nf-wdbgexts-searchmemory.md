---
UID : NF:wdbgexts.SearchMemory
title : SearchMemory function
author : windows-driver-content
description : The SearchMemory function searches the target's virtual memory for a specified pattern of bytes.
old-location : debugger\searchmemory.htm
old-project : debugger
ms.assetid : 7e07c47e-803b-44fa-9d0f-aa86475246d2
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : SearchMemory, wdbgexts/SearchMemory, WdbgExts_Ref_4eb909e5-edfd-487c-851c-812b15274c66.xml, SearchMemory function [Windows Debugging], debugger.searchmemory
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdbgexts.h
req.include-header : Wdbgexts.h, Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXT_TDOP
req.product : Windows 10 or later.
---


# SearchMemory function
The <b>SearchMemory</b> function searches the target's virtual memory for a specified pattern of bytes.

## Syntax

````
__inline VOID SearchMemory(
   ULONG64  SearchAddress,
   ULONG64  SearchLength,
   ULONG    PatternLength,
   PVOID    Pattern,
   PULONG64 FoundAddress
);
````

## Parameters

`SearchAddress`

Specifies the address in the target's virtual memory from which to start the search.

`SearchLength`

Specifies the size, in bytes, of the memory to search.  For a successful match, the pattern must be found before <i>SearchLength</i> bytes have been examined.

`PatternLength`

Specifies the size, in bytes, of the pattern to search for.

`Pattern`

Specifies the pattern to search for.

`FoundAddress`

Receives the location of the pattern, found in the target's virtual memory.  If the pattern was not found, the value in <i>FoundAddress</i> is unchanged by this function.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |