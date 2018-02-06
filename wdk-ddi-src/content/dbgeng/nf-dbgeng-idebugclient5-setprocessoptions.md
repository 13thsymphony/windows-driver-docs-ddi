---
UID: NF:dbgeng.IDebugClient5.SetProcessOptions
title: IDebugClient5::SetProcessOptions method
author: windows-driver-content
description: The SetProcessOptions method sets the process options affecting the current process.
old-location: debugger\setprocessoptions.htm
old-project: debugger
ms.assetid: c077e2cc-b234-4393-ab8c-d0b8199515e3
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient::SetProcessOptions, IDebugClient4::SetProcessOptions, debugger.setprocessoptions, dbgeng/IDebugClient5::SetProcessOptions, SetProcessOptions method [Windows Debugging], IDebugClient2 interface, IDebugClient4 interface [Windows Debugging], SetProcessOptions method, IDebugClient2::SetProcessOptions, SetProcessOptions method [Windows Debugging], IDebugClient4 interface, IDebugClient5::SetProcessOptions, SetProcessOptions method [Windows Debugging], IDebugClient interface, IDebugClient3 interface [Windows Debugging], SetProcessOptions method, IDebugClient5 interface [Windows Debugging], SetProcessOptions method, dbgeng/IDebugClient2::SetProcessOptions, IDebugClient5, dbgeng/IDebugClient4::SetProcessOptions, dbgeng/IDebugClient::SetProcessOptions, SetProcessOptions method [Windows Debugging], IDebugClient interface [Windows Debugging], SetProcessOptions method, IDebugClient2 interface [Windows Debugging], SetProcessOptions method, IDebugClient3::SetProcessOptions, SetProcessOptions method [Windows Debugging], IDebugClient5 interface, SetProcessOptions, SetProcessOptions method [Windows Debugging], IDebugClient3 interface, IDebugClient_d9936a28-08c3-4c4c-ba2b-accc9443b825.xml, dbgeng/IDebugClient3::SetProcessOptions
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
-	IDebugClient.SetProcessOptions
-	IDebugClient2.SetProcessOptions
-	IDebugClient3.SetProcessOptions
-	IDebugClient4.SetProcessOptions
-	IDebugClient5.SetProcessOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# SetProcessOptions method
The <b>SetProcessOptions</b> method sets the process options affecting the current process.

## Syntax

````
HRESULT SetProcessOptions(
  [in] ULONG Options
);
````

## Parameters

`Options`

Specifies a set of flags that will become the new process options for the current process.  For details on these options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>.


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
</table>

## Remarks

This method is available only in live user-mode debugging.

Some of the process options are global options, others are specific to the current process.

If any process options are modified, the engine will notify the event callbacks by calling their <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> method with the DEBUG_CES_PROCESS_OPTIONS flag set.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548163">GetProcessOptions</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554505">RemoveProcessOptions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537917">AddProcessOptions</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::SetProcessOptions method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>