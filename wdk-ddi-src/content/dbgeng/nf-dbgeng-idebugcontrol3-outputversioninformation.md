---
UID: NF:dbgeng.IDebugControl3.OutputVersionInformation
title: IDebugControl3::OutputVersionInformation method
author: windows-driver-content
description: The OutputVersionInformation method prints version information about the debugger engine to the debugger console.
old-location: debugger\outputversioninformation.htm
old-project: debugger
ms.assetid: cbf688b4-a174-4ab0-af98-2c0db1b2ab3a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl2 interface [Windows Debugging], OutputVersionInformation method, OutputVersionInformation method [Windows Debugging], IDebugControl3, dbgeng/IDebugControl2::OutputVersionInformation, OutputVersionInformation method [Windows Debugging], IDebugControl interface, IDebugControl interface [Windows Debugging], OutputVersionInformation method, dbgeng/IDebugControl::OutputVersionInformation, debugger.outputversioninformation, OutputVersionInformation, IDebugControl_ea568b24-944d-4ed8-abd6-24b7c7771a1e.xml, dbgeng/IDebugControl3::OutputVersionInformation, IDebugControl::OutputVersionInformation, IDebugControl3 interface [Windows Debugging], OutputVersionInformation method, IDebugControl3::OutputVersionInformation, IDebugControl2::OutputVersionInformation, IDebugControl2, IDebugControl, OutputVersionInformation method [Windows Debugging], IDebugControl3 interface, OutputVersionInformation method [Windows Debugging], IDebugControl2 interface
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
-	IDebugControl.OutputVersionInformation
-	IDebugControl2.OutputVersionInformation
-	IDebugControl3.OutputVersionInformation
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# OutputVersionInformation method
The <b>OutputVersionInformation</b> method prints version information about the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> to the debugger console.

## Syntax

````
HRESULT OutputVersionInformation(
  [in] ULONG OutputControl
);
````

## Parameters

`OutputControl`

Specifies where to send the output.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.


## Return Value

This method may also return other error values, including error values caused by the engine being busy.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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

The information that is sent to the output can include the mode of the debugger, the path and version of the debugger DLLs, the extension DLL search path, the extension DLL chain, and the version of the operating system that is running on the host computer.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |