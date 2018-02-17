---
UID: NF:dbgeng.IDebugControl3.GetCodeLevel
title: IDebugControl3::GetCodeLevel method
author: windows-driver-content
description: The GetCodeLevel method returns the current code level and is mainly used when stepping through code.
old-location: debugger\getcodelevel.htm
old-project: debugger
ms.assetid: 965565ee-ef4c-4a1d-a6f1-77b6d63c6ee8
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl interface [Windows Debugging], GetCodeLevel method, IDebugControl3 interface [Windows Debugging], GetCodeLevel method, GetCodeLevel method [Windows Debugging], IDebugControl2 interface, GetCodeLevel method [Windows Debugging], IDebugControl interface, IDebugControl3, IDebugControl::GetCodeLevel, GetCodeLevel, IDebugControl_8533dd3f-f004-4d89-9f02-b7835fc6169e.xml, debugger.getcodelevel, IDebugControl3::GetCodeLevel, dbgeng/IDebugControl::GetCodeLevel, IDebugControl2 interface [Windows Debugging], GetCodeLevel method, dbgeng/IDebugControl3::GetCodeLevel, GetCodeLevel method [Windows Debugging], GetCodeLevel method [Windows Debugging], IDebugControl3 interface, dbgeng/IDebugControl2::GetCodeLevel, IDebugControl2, IDebugControl, IDebugControl2::GetCodeLevel
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
-	IDebugControl.GetCodeLevel
-	IDebugControl2.GetCodeLevel
-	IDebugControl3.GetCodeLevel
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetCodeLevel method
The <b>GetCodeLevel</b> method returns the current code level and is mainly used when stepping through code.

## Syntax

````
HRESULT GetCodeLevel(
  [out] PULONG Level
);
````

## Parameters

`Level`

Receives the current code level.  <i>Level</i> can take one of the values in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_LEVEL_SOURCE

</td>
<td>
<i>Source mode</i>.  When stepping through code on the target, the size of a single step will be a line of source code.

</td>
</tr>
<tr>
<td>
DEBUG_LEVEL_ASSEMBLY

</td>
<td>
<i>Assembly mode</i>.  When stepping through code on the target, the size of a single step will be a single processor instruction.

</td>
</tr>
</table>


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

For more information about the code level, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556629">SetCodeLevel</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetCodeLevel method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>