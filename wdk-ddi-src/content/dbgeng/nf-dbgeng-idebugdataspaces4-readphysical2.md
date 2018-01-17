---
UID: NF:dbgeng.IDebugDataSpaces4.ReadPhysical2
title: IDebugDataSpaces4::ReadPhysical2 method
author: windows-driver-content
description: The ReadPhysical2 method reads the target's memory from the specified physical address.
old-location: debugger\readphysical2.htm
old-project: debugger
ms.assetid: ad376a6f-b8e3-40ba-9b00-df1410c1293c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::ReadPhysical2, ReadPhysical2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugDataSpaces4.ReadPhysical2
req.alt-loc: dbgeng.h
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces4::ReadPhysical2 method



## -description
The <b>ReadPhysical2</b> method reads the target's memory from the specified physical address.



## -syntax

````
HRESULT ReadPhysical2(
  [in]            ULONG64 Offset,
  [in]            ULONG   Flags,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````


## -parameters

### -param Offset [in]

Specifies the physical address of the memory to read.


### -param Flags [in]

Specifies the properties of the physical memory to be read.  This must match the way the physical memory was advertised to the operating system on the target.  Possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_DEFAULT

</td>
<td>
Use the default memory caching.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_CACHED

</td>
<td>
The physical memory is cached.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_UNCACHED

</td>
<td>
The physical memory is uncached.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_WRITE_COMBINED

</td>
<td>
The physical memory is write-combined.

</td>
</tr>
</table>
 


### -param Buffer [out]

Receives the memory that is read.


### -param BufferSize [in]

Specifies the size, in bytes, of the <i>Buffer</i> buffer.  This is the maximum number of bytes that will be read.


### -param BytesRead [out, optional]

Receives the number of bytes read from the target's memory.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
This method is only available in kernel-mode debugging.

The flags DEBUG_PHYSICAL_CACHED, DEBUG_PHYSICAL_UNCACHED, and DEBUG_PHYSICAL_WRITE_COMBINED can only be used when the target is a live kernel target that is being debugged in the standard way (using a COM port, 1394 bus, or named pipe).


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554313">ReadPhysical</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561441">WritePhysical2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces4::ReadPhysical2 method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

