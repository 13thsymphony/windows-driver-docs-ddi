---
UID: NF:dbgeng.IDebugControl.ReadBugCheckData
title: IDebugControl::ReadBugCheckData method
author: windows-driver-content
description: The ReadBugCheckData method reads the kernel bug check code and related parameters.
old-location: debugger\readbugcheckdata.htm
old-project: Debugger
ms.assetid: 3ede32f5-9671-4f38-a33f-96536300267b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.readbugcheckdata, IDebugControl, ReadBugCheckData method [Windows Debugging], IDebugControl interface, dbgeng/IDebugControl2::ReadBugCheckData, IDebugControl3::ReadBugCheckData, dbgeng/IDebugControl3::ReadBugCheckData, IDebugControl3 interface [Windows Debugging], ReadBugCheckData method, ReadBugCheckData method [Windows Debugging], IDebugControl3 interface, IDebugControl interface [Windows Debugging], ReadBugCheckData method, IDebugControl::ReadBugCheckData, dbgeng/IDebugControl::ReadBugCheckData, IDebugControl2 interface [Windows Debugging], ReadBugCheckData method, IDebugControl_d96bd559-1a82-4d5d-8aa8-7a32242f2b68.xml, ReadBugCheckData method [Windows Debugging], IDebugControl2 interface, IDebugControl2::ReadBugCheckData, ReadBugCheckData method [Windows Debugging], ReadBugCheckData
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
-	IDebugControl.ReadBugCheckData
-	IDebugControl2.ReadBugCheckData
-	IDebugControl3.ReadBugCheckData
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# ReadBugCheckData method
The <b>ReadBugCheckData</b> method reads the kernel bug check code and related parameters.

## Syntax

````
HRESULT ReadBugCheckData(
  [out] PULONG   Code,
  [out] PULONG64 Arg1,
  [out] PULONG64 Arg2,
  [out] PULONG64 Arg3,
  [out] PULONG64 Arg4
);
````

## Parameters

`Code`

Receives the bug check code.

`Arg1`

Receives the first parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.

`Arg2`

Receives the second parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.

`Arg3`

Receives the third parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.

`Arg4`

Receives the fourth parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.


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

For more information about bug checks, including a list of bug check codes and their interpretations, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450912">Bug Checks (Blue Screens)</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |