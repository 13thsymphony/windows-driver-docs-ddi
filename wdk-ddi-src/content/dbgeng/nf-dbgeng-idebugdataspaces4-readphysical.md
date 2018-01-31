---
UID : NF:dbgeng.IDebugDataSpaces4.ReadPhysical
title : IDebugDataSpaces4::ReadPhysical method
author : windows-driver-content
description : The ReadPhysical method reads the target's memory from the specified physical address.
old-location : debugger\readphysical3.htm
old-project : debugger
ms.assetid : 8df51985-9208-46ce-8802-6bc5ec707ab2
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : ReadPhysical method [Windows Debugging], ReadPhysical method [Windows Debugging], IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces4::ReadPhysical, IDebugDataSpaces_5be1f680-1177-4cdf-a4d8-5868644a51af.xml, IDebugDataSpaces::ReadPhysical, ReadPhysical method [Windows Debugging], IDebugDataSpaces3 interface, dbgeng/IDebugDataSpaces2::ReadPhysical, IDebugDataSpaces3::ReadPhysical, ReadPhysical, IDebugDataSpaces3 interface [Windows Debugging], ReadPhysical method, IDebugDataSpaces4::ReadPhysical, IDebugDataSpaces2::ReadPhysical, ReadPhysical method [Windows Debugging], IDebugDataSpaces interface, IDebugDataSpaces interface [Windows Debugging], ReadPhysical method, IDebugDataSpaces4, debugger.readphysical3, ReadPhysical method [Windows Debugging], IDebugDataSpaces2 interface, IDebugDataSpaces4 interface [Windows Debugging], ReadPhysical method, dbgeng/IDebugDataSpaces::ReadPhysical, dbgeng/IDebugDataSpaces3::ReadPhysical, IDebugDataSpaces2 interface [Windows Debugging], ReadPhysical method
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
req.typenames : DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# ReadPhysical method
The <b>ReadPhysical</b> method reads the target's memory from the specified physical address.

## Syntax

````
HRESULT ReadPhysical(
  [in]            ULONG64 Offset,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````

## Parameters

`Offset`

Specifies the physical address of the memory to read.

`Buffer`

Receives the memory that is read.

`BufferSize`

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be read.

`BytesRead`

Receives the number of bytes read from the target's memory.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.


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
The method was successful.

</td>
</tr>
</table> 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

This method is only available in kernel-mode debugging.

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