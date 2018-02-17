---
UID: NF:dbgeng.IDebugDataSpaces.ReadVirtualUncached
title: IDebugDataSpaces::ReadVirtualUncached method
author: windows-driver-content
description: The ReadVirtualUncached method reads memory from the target's virtual address space.
old-location: debugger\readvirtualuncached.htm
old-project: debugger
ms.assetid: 91674220-3160-40d2-9d68-56d854244711
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugDataSpaces3::ReadVirtualUncached, IDebugDataSpaces::ReadVirtualUncached, dbgeng/IDebugDataSpaces2::ReadVirtualUncached, ReadVirtualUncached method [Windows Debugging], IDebugDataSpaces3 interface, IDebugDataSpaces4 interface [Windows Debugging], ReadVirtualUncached method, ReadVirtualUncached method [Windows Debugging], IDebugDataSpaces interface, IDebugDataSpaces4::ReadVirtualUncached, IDebugDataSpaces2 interface [Windows Debugging], ReadVirtualUncached method, ReadVirtualUncached method [Windows Debugging], IDebugDataSpaces3 interface [Windows Debugging], ReadVirtualUncached method, IDebugDataSpaces interface [Windows Debugging], ReadVirtualUncached method, IDebugDataSpaces_265817a7-d690-4b8c-957f-06ec5d4f2f08.xml, ReadVirtualUncached method [Windows Debugging], IDebugDataSpaces4 interface, IDebugDataSpaces, IDebugDataSpaces2::ReadVirtualUncached, ReadVirtualUncached, debugger.readvirtualuncached, IDebugDataSpaces3::ReadVirtualUncached, ReadVirtualUncached method [Windows Debugging], IDebugDataSpaces2 interface, dbgeng/IDebugDataSpaces4::ReadVirtualUncached, dbgeng/IDebugDataSpaces::ReadVirtualUncached
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugDataSpaces.ReadVirtualUncached
-	IDebugDataSpaces2.ReadVirtualUncached
-	IDebugDataSpaces3.ReadVirtualUncached
-	IDebugDataSpaces4.ReadVirtualUncached
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# ReadVirtualUncached method
The <b>ReadVirtualUncached</b> method reads memory from the target's virtual address space.

## Syntax

````
HRESULT ReadVirtualUncached(
  [in]            ULONG64 Offset,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````

## Parameters

`Offset`

Specifies the location in the target's virtual address space to be read.

`Buffer`

Specifies the buffer to read the memory into.

`BufferSize`

Specifies the size in bytes of the buffer.  This is also the number of bytes being requested.

`BytesRead`

Receives the number of bytes that were read.  If it is set to <b>NULL</b>, this information is not returned.


## Return Value

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  It is possible that <i>BytesRead</i> is less than <i>BufferSize</i>, but at least one byte of data is being returned.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

This method fills the buffer with the contents of the memory in the target's virtual address space.

This method behaves identically to <a href="https://msdn.microsoft.com/library/windows/hardware/ff554359">ReadVirtual</a>, except that it avoids using the virtual memory cache.  It is therefore useful for reading inherently volatile virtual memory, such as memory-mapped device areas, without contaminating or invalidating the cache.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554359">ReadVirtual</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561473">WriteVirtualUncached</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces.md">IDebugDataSpaces</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces::ReadVirtualUncached method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>