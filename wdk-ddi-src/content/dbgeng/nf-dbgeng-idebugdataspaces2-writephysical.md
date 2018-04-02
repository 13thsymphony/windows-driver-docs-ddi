---
UID: NF:dbgeng.IDebugDataSpaces2.WritePhysical
title: IDebugDataSpaces2::WritePhysical method
author: windows-driver-content
description: The WritePhysical method writes data to the specified physical address in the target's memory.
old-location: debugger\writephysical3.htm
old-project: debugger
ms.assetid: ec691a7c-a569-49dd-af13-bfbf403be297
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugDataSpaces interface [Windows Debugging], WritePhysical method, IDebugDataSpaces2, IDebugDataSpaces2 interface [Windows Debugging], WritePhysical method, IDebugDataSpaces2::WritePhysical, IDebugDataSpaces3 interface [Windows Debugging], WritePhysical method, IDebugDataSpaces3::WritePhysical, IDebugDataSpaces4 interface [Windows Debugging], WritePhysical method, IDebugDataSpaces4::WritePhysical, IDebugDataSpaces::WritePhysical, IDebugDataSpaces_0e781d56-64f8-4518-b748-5afe9f43c429.xml, WritePhysical method [Windows Debugging], WritePhysical method [Windows Debugging], IDebugDataSpaces interface, WritePhysical method [Windows Debugging], IDebugDataSpaces2 interface, WritePhysical method [Windows Debugging], IDebugDataSpaces3 interface, WritePhysical method [Windows Debugging], IDebugDataSpaces4 interface, WritePhysical,IDebugDataSpaces2.WritePhysical, dbgeng/IDebugDataSpaces2::WritePhysical, dbgeng/IDebugDataSpaces3::WritePhysical, dbgeng/IDebugDataSpaces4::WritePhysical, dbgeng/IDebugDataSpaces::WritePhysical, debugger.writephysical3
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Dbgeng.h
api_name:
-	IDebugDataSpaces.WritePhysical
-	IDebugDataSpaces2.WritePhysical
-	IDebugDataSpaces3.WritePhysical
-	IDebugDataSpaces4.WritePhysical
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugDataSpaces2::WritePhysical method
The <b>WritePhysical</b> method writes data to the specified physical address in the target's memory.

## Syntax

```
HRESULT WritePhysical(
  ULONG64 Offset,
  PVOID   Buffer,
  ULONG   BufferSize,
  PULONG  BytesWritten
);
```

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