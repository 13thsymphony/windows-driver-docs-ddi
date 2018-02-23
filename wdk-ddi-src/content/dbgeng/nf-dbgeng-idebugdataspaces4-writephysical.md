---
UID: NF:dbgeng.IDebugDataSpaces4.WritePhysical
title: IDebugDataSpaces4::WritePhysical method
author: windows-driver-content
description: The WritePhysical method writes data to the specified physical address in the target's memory.
old-location: debugger\writephysical3.htm
old-project: Debugger
ms.assetid: ec691a7c-a569-49dd-af13-bfbf403be297
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugDataSpaces3::WritePhysical, dbgeng/IDebugDataSpaces2::WritePhysical, WritePhysical method [Windows Debugging], IDebugDataSpaces interface, dbgeng/IDebugDataSpaces4::WritePhysical, IDebugDataSpaces::WritePhysical, dbgeng/IDebugDataSpaces::WritePhysical, dbgeng/IDebugDataSpaces3::WritePhysical, IDebugDataSpaces2::WritePhysical, IDebugDataSpaces2 interface [Windows Debugging], WritePhysical method, IDebugDataSpaces3, IDebugDataSpaces4::WritePhysical, IDebugDataSpaces_0e781d56-64f8-4518-b748-5afe9f43c429.xml, IDebugDataSpaces3 interface [Windows Debugging], WritePhysical method, WritePhysical method [Windows Debugging], WritePhysical method [Windows Debugging], IDebugDataSpaces4 interface, IDebugDataSpaces, WritePhysical method [Windows Debugging], IDebugDataSpaces3 interface, WritePhysical, IDebugDataSpaces4, IDebugDataSpaces2, IDebugDataSpaces4 interface [Windows Debugging], WritePhysical method, debugger.writephysical3, IDebugDataSpaces interface [Windows Debugging], WritePhysical method, WritePhysical method [Windows Debugging], IDebugDataSpaces2 interface
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
-	Dbgeng.h
apiname:
-	IDebugDataSpaces.WritePhysical
-	IDebugDataSpaces2.WritePhysical
-	IDebugDataSpaces3.WritePhysical
-	IDebugDataSpaces4.WritePhysical
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# WritePhysical method
The <b>WritePhysical</b> method writes data to the specified physical address in the target's memory.

## Syntax

````
HRESULT WritePhysical(
  [in]            ULONG64 Offset,
  [in]            PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesWritten
);
````

## Parameters

`Offset`

Specifies the physical address of the memory to write the data to.

`Buffer`

Specifies the data to write.

`BufferSize`

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be written.

`BytesWritten`

Receives the number of bytes written to the target's memory.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.


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
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |