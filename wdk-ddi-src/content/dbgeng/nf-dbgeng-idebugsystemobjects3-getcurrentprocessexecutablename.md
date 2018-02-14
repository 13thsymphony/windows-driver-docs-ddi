---
UID: NF:dbgeng.IDebugSystemObjects3.GetCurrentProcessExecutableName
title: IDebugSystemObjects3::GetCurrentProcessExecutableName method
author: windows-driver-content
description: The GetCurrentProcessExecutableName method returns the name of executable file loaded in the current process.
old-location: debugger\getcurrentprocessexecutablename.htm
old-project: debugger
ms.assetid: ea968316-a53d-4ab1-966a-5c699ffb8f2a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects::GetCurrentProcessExecutableName, IDebugSystemObjects_2659a668-4ecb-44de-b287-b4adc830f8c4.xml, IDebugSystemObjects2::GetCurrentProcessExecutableName, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentProcessExecutableName method, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentProcessExecutableName method, dbgeng/IDebugSystemObjects::GetCurrentProcessExecutableName, GetCurrentProcessExecutableName method [Windows Debugging], IDebugSystemObjects3 interface, dbgeng/IDebugSystemObjects4::GetCurrentProcessExecutableName, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentProcessExecutableName method, IDebugSystemObjects interface [Windows Debugging], GetCurrentProcessExecutableName method, IDebugSystemObjects3::GetCurrentProcessExecutableName, dbgeng/IDebugSystemObjects3::GetCurrentProcessExecutableName, GetCurrentProcessExecutableName, GetCurrentProcessExecutableName method [Windows Debugging], debugger.getcurrentprocessexecutablename, dbgeng/IDebugSystemObjects2::GetCurrentProcessExecutableName, IDebugSystemObjects4::GetCurrentProcessExecutableName, GetCurrentProcessExecutableName method [Windows Debugging], IDebugSystemObjects interface, IDebugSystemObjects2, GetCurrentProcessExecutableName method [Windows Debugging], IDebugSystemObjects4 interface, IDebugSystemObjects3, IDebugSystemObjects, GetCurrentProcessExecutableName method [Windows Debugging], IDebugSystemObjects2 interface
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
-	IDebugSystemObjects.GetCurrentProcessExecutableName
-	IDebugSystemObjects2.GetCurrentProcessExecutableName
-	IDebugSystemObjects3.GetCurrentProcessExecutableName
-	IDebugSystemObjects4.GetCurrentProcessExecutableName
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetCurrentProcessExecutableName method
The <b>GetCurrentProcessExecutableName</b>  method returns the name of executable file loaded in the current process.

## Syntax

````
HRESULT GetCurrentProcessExecutableName(
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG ExeSize
);
````

## Parameters

`Buffer`

Receives the name of the executable file.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

`BufferSize`

Specifies the size in characters of the buffer <i>Buffer</i>.

`ExeSize`

Receives the size in characters of the name of the executable file.  If <i>ExeSize</i> is <b>NULL</b>, this information is not returned.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not large enough to hold the name of the executable file and it was truncated.

</td>
</tr>
</table>

## Remarks

These methods are only available in user-mode debugging.

If the engine cannot determine the name of the executable file, it writes the string "?NoImage?" to the buffer.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |