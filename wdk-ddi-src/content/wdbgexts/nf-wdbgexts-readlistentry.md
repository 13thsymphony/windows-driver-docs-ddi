---
UID: NF.wdbgexts.ReadListEntry
title: ReadListEntry function
author: windows-driver-content
description: The ReadListEntry function reads a doubly-linked list entry from the target's memory.
old-location: debugger\readlistentry.htm
old-project: debugger
ms.assetid: b5bfbb6d-4797-4e5f-bc66-398527b13d85
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: ReadListEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h, Winnt.h, Ntdef.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ReadListEntry
req.alt-loc: wdbgexts.h
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
req.product: Windows 10 or later.
---

# ReadListEntry function



## -description
The <b>ReadListEntry</b> function reads a doubly-linked list entry from the target's memory.


## -syntax

````
__inline ULONG ReadListEntry(
   ULONG64       Address,
   PLIST_ENTRY64 List
);
````


## -parameters

### -param Address 

Specifies the address of the list entry in the target.  If the target uses 32-bit pointers, this should be the address of a LIST_ENTRY32 structure.  If the target uses 64-bit pointers, this should be the address of a LIST_ENTRY64 structure.

### -param List 

Receives a LIST_ENTRY64 structure that contains pointers to the previous and next entries in the list.  If the target uses 32-bit pointers, they are sign-extended to 64 bits.

## -returns
If the function succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.

## -remarks
For more information about the LIST_ENTRY structures, see the Windows Driver Kit (WDK) documentation.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).


LIST_ENTRY64 and LIST_ENTRY32 are defined in <b>winnt.h</b>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdbgexts.h (include Wdbgexts.h, Dbgeng.h, Winnt.h, or Ntdef.h)</dt>
</dl>
</td>
</tr>
</table>