---
UID: NF:dbgeng.IDebugClient5.GetExitCode
title: IDebugClient5::GetExitCode method
author: windows-driver-content
description: The GetExitCode method returns the exit code of the current process if that process has already run through to completion.
old-location: debugger\getexitcode.htm
old-project: debugger
ms.assetid: faa5cc0f-a99c-42fb-ab8f-a37c31bc4dde
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient5, GetExitCode method [Windows Debugging], IDebugClient3 interface, GetExitCode method [Windows Debugging], GetExitCode method [Windows Debugging], IDebugClient4 interface, IDebugClient_c0198b4c-b627-42c9-80eb-15db22156293.xml, IDebugClient3::GetExitCode, IDebugClient::GetExitCode, GetExitCode method [Windows Debugging], IDebugClient interface, IDebugClient4::GetExitCode, IDebugClient5 interface [Windows Debugging], GetExitCode method, IDebugClient2 interface [Windows Debugging], GetExitCode method, dbgeng/IDebugClient2::GetExitCode, dbgeng/IDebugClient3::GetExitCode, debugger.getexitcode, GetExitCode, IDebugClient2, dbgeng/IDebugClient4::GetExitCode, IDebugClient4, IDebugClient interface [Windows Debugging], GetExitCode method, GetExitCode method [Windows Debugging], IDebugClient5 interface, dbgeng/IDebugClient5::GetExitCode, IDebugClient3, GetExitCode method [Windows Debugging], IDebugClient2 interface, IDebugClient, IDebugClient4 interface [Windows Debugging], GetExitCode method, IDebugClient2::GetExitCode, IDebugClient5::GetExitCode, dbgeng/IDebugClient::GetExitCode, IDebugClient3 interface [Windows Debugging], GetExitCode method
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
-	IDebugClient.GetExitCode
-	IDebugClient2.GetExitCode
-	IDebugClient3.GetExitCode
-	IDebugClient4.GetExitCode
-	IDebugClient5.GetExitCode
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetExitCode method
The <b>GetExitCode</b> method returns the exit code of the current process if that process has already run through to completion.

## Syntax

````
HRESULT GetExitCode(
  [out] PULONG Code
);
````

## Parameters

`Code`

Receives the exit code of the process.  If the process is still running, <i>Code</i> will be set to STILL_ACTIVE.


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
The process is still running.

</td>
</tr>
</table>

## Remarks

This method is available only for live user-mode debugging.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |