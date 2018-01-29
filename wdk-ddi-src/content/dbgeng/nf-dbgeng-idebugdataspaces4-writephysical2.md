---
UID : NF:dbgeng.IDebugDataSpaces4.WritePhysical2
title : IDebugDataSpaces4::WritePhysical2 method
author : windows-driver-content
description : The WritePhysical2 method writes data to the specified physical address in the target's memory.
old-location : debugger\writephysical2.htm
old-project : debugger
ms.assetid : 15a83343-b95b-4f79-b4f2-ed2ad60d170e
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugDataSpaces4::WritePhysical2, WritePhysical2, WritePhysical2 method [Windows Debugging], IDebugDataSpaces4 interface [Windows Debugging], WritePhysical2 method, IDebugDataSpaces_bc084790-b047-4257-b7fd-578fd4454747.xml, IDebugDataSpaces4, dbgeng/IDebugDataSpaces4::WritePhysical2, WritePhysical2 method [Windows Debugging], IDebugDataSpaces4 interface, debugger.writephysical2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
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
req.lib : dbgeng.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# WritePhysical2 method
The <b>WritePhysical2</b> method writes data to the specified physical address in the target's memory.

## Syntax

````
HRESULT WritePhysical2(
  [in]            ULONG64 Offset,
  [in]            ULONG   Flags,
  [in]            PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesWritten
);
````

## Parameters

`Offset`

Specifies the physical address of the memory to write the data to.

`Flags`

Specifies the properties of the physical memory to be written to.  This must match the way the physical memory was advertised to the operating system on the target.  Possible values are listed in the following table.
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

`Buffer`

Specifies the data to write.

`BufferSize`

Specifies the size, in bytes, of the <i>Buffer</i> buffer.  This is the maximum number of bytes that will be written.

`BytesWritten`

Receives the number of bytes written to the target's memory.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.


## Return Value

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
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
The method was successful.

</td>
</tr>
</table>

## Remarks

This method is only available in kernel-mode debugging.

The flags DEBUG_PHYSICAL_CACHED, DEBUG_PHYSICAL_UNCACHED, and DEBUG_PHYSICAL_WRITE_COMBINED can only be used when the target is a live kernel target that is being debugged in the standard way (using a COM port, 1394 bus, or named pipe).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561432">WritePhysical</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561441">WritePhysical2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces4::WritePhysical2 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>