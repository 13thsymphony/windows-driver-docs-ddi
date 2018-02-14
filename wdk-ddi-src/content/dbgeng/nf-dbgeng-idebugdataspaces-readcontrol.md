---
UID: NF:dbgeng.IDebugDataSpaces.ReadControl
title: IDebugDataSpaces::ReadControl method
author: windows-driver-content
description: The ReadControl method reads implementation-specific system data.
old-location: debugger\readcontrol.htm
old-project: debugger
ms.assetid: 52f65e2a-97a7-4c1c-a021-208bc2520b7d
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugDataSpaces_bca10b0c-a1bb-49bf-aa76-4e790a907a9f.xml, debugger.readcontrol, ReadControl method [Windows Debugging], IDebugDataSpaces2 interface, ReadControl method [Windows Debugging], IDebugDataSpaces interface, IDebugDataSpaces3 interface [Windows Debugging], ReadControl method, dbgeng/IDebugDataSpaces4::ReadControl, IDebugDataSpaces interface [Windows Debugging], ReadControl method, dbgeng/IDebugDataSpaces::ReadControl, ReadControl method [Windows Debugging], IDebugDataSpaces, IDebugDataSpaces::ReadControl, ReadControl method [Windows Debugging], IDebugDataSpaces4 interface, IDebugDataSpaces4::ReadControl, dbgeng/IDebugDataSpaces2::ReadControl, IDebugDataSpaces3::ReadControl, dbgeng/IDebugDataSpaces3::ReadControl, IDebugDataSpaces2 interface [Windows Debugging], ReadControl method, ReadControl method [Windows Debugging], IDebugDataSpaces3 interface, IDebugDataSpaces2::ReadControl, ReadControl, IDebugDataSpaces4 interface [Windows Debugging], ReadControl method
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
-	IDebugDataSpaces.ReadControl
-	IDebugDataSpaces2.ReadControl
-	IDebugDataSpaces3.ReadControl
-	IDebugDataSpaces4.ReadControl
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# ReadControl method
The <b>ReadControl</b> method reads implementation-specific system data.

## Syntax

````
HRESULT ReadControl(
  [in]            ULONG   Processor,
  [in]            ULONG64 Offset,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````

## Parameters

`Processor`

Specifies the processor whose information is to be read.

`Offset`

Specifies the offset in the control space of the memory to read.

`Buffer`

Receives the data read from the control-space memory.

`BufferSize`

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be read.

`BytesRead`

Receives the number of bytes returned in the buffer <i>Buffer</i>.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.


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