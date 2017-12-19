---
UID: NF.wdbgexts.WritePhysicalWithFlags
title: WritePhysicalWithFlags function
author: windows-driver-content
description: The WritePhysicalWithFlags function writes to physical memory.
old-location: debugger\writephysicalwithflags.htm
old-project: Debugger
ms.assetid: ae679f76-2e26-43f2-a097-1e158fbc0cc7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: WritePhysicalWithFlags
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
req.alt-api: WritePhysicalWithFlags
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

# WritePhysicalWithFlags function



## -description
The <b>WritePhysicalWithFlags</b> function writes to physical memory.



## -syntax

````
VOID WritePhysicalWithFlags(
   ULONG64 address,
   PVOID   buf,
   ULONG   size,
   ULONG   flags,
   PULONG  sizew
);
````


## -parameters

### -param address 

Specifies the physical address to write.


### -param buf 

Specifies the address of an array of bytes to hold the data that is  written.


### -param size 

Specifies the number of bytes to write. 


### -param flags 

Specifies the properties of the physical memory to be written to.  This must match the way the physical memory was advertised to the operating system on the target.  Possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
PHYS_FLAG_DEFAULT

</td>
<td>
Use the default memory caching.

</td>
</tr>
<tr>
<td>
PHYS_FLAG_CACHED

</td>
<td>
The physical memory is cached.

</td>
</tr>
<tr>
<td>
PHYS_FLAG_UNCACHED

</td>
<td>
The physical memory is uncached.

</td>
</tr>
<tr>
<td>
PHYS_FLAG_WRITE_COMBINED

</td>
<td>
The physical memory is write-combined.

</td>
</tr>
</table>
 


### -param sizew 

Receives the number of bytes actually written.


## -returns
None


## -remarks
For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.


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
<dt>Wdbgexts.h (include Wdbgexts.h or Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="debugger.writephysical">WritePhysical</a>
</dt>
<dt>
<a href="debugger.readphysicalwithflags">ReadPhysicalWithFlags</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20WritePhysicalWithFlags function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

