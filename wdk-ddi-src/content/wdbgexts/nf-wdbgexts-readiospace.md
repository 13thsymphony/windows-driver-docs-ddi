---
UID: NF:wdbgexts.ReadIoSpace
title: ReadIoSpace function
author: windows-driver-content
description: The ReadIoSpace function reads from the system I/O locations.
old-location: debugger\readiospace.htm
old-project: debugger
ms.assetid: 31118f7f-fcc4-45f9-a248-a1d6f929f3a2
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: wdbgexts/ReadIoSpace, ReadIoSpace function [Windows Debugging], WdbgExts_Ref_e34c76a6-de5d-4347-90a7-959d5392680e.xml, ReadIoSpace, debugger.readiospace
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
-	ReadIoSpace
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---


# ReadIoSpace function
The <b>ReadIoSpace</b> function reads from the system I/O locations.

## Syntax

````
__inline VOID ReadIoSpace(
   ULONG  address,
   PULONG data,
   PULONG size
);
````

## Parameters

`address`

Specifies the I/O address to read from.

`data`

Specifies the address of a variable to hold the data read. This must be at least the number of bytes contained in <i>size</i>.

`size`

Specifies the address of a variable that contains the number of bytes to read (1, 2, or 4 only). After the data is read, <i>size</i> will contain the number of bytes actually read.


## Return Value

None

## Remarks

If you are writing 64-bit code, you should use <a href="..\wdbgexts\nf-wdbgexts-readiospace64.md">ReadIoSpace64</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |
| **Library** | NtosKrnl.exe |