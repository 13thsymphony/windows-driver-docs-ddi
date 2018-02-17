---
UID: NF:dbgeng.IDebugClient4.WaitForProcessServerEnd
title: IDebugClient4::WaitForProcessServerEnd method
author: windows-driver-content
description: The WaitForProcessServerEnd method waits for a local process server to exit.
old-location: debugger\waitforprocessserverend.htm
old-project: debugger
ms.assetid: 19573307-0192-47bd-86a0-9c7721d16c5e
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient2::WaitForProcessServerEnd, IDebugClient2 interface [Windows Debugging], WaitForProcessServerEnd method, IDebugClient3, WaitForProcessServerEnd method [Windows Debugging], IDebugClient4::WaitForProcessServerEnd, WaitForProcessServerEnd, WaitForProcessServerEnd method [Windows Debugging], IDebugClient3 interface, WaitForProcessServerEnd method [Windows Debugging], IDebugClient5 interface, IDebugClient3 interface [Windows Debugging], WaitForProcessServerEnd method, IDebugClient3::WaitForProcessServerEnd, IDebugClient_ac54327c-85c5-41ab-906f-605d374a0e2d.xml, dbgeng/IDebugClient4::WaitForProcessServerEnd, dbgeng/IDebugClient5::WaitForProcessServerEnd, IDebugClient2, dbgeng/IDebugClient3::WaitForProcessServerEnd, IDebugClient4 interface [Windows Debugging], WaitForProcessServerEnd method, WaitForProcessServerEnd method [Windows Debugging], IDebugClient4 interface, IDebugClient4, dbgeng/IDebugClient2::WaitForProcessServerEnd, IDebugClient5::WaitForProcessServerEnd, debugger.waitforprocessserverend, IDebugClient5 interface [Windows Debugging], WaitForProcessServerEnd method, WaitForProcessServerEnd method [Windows Debugging], IDebugClient2 interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Winbase.h
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
-	IDebugClient2.WaitForProcessServerEnd
-	IDebugClient3.WaitForProcessServerEnd
-	IDebugClient4.WaitForProcessServerEnd
-	IDebugClient5.WaitForProcessServerEnd
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# WaitForProcessServerEnd method
The <b>WaitForProcessServerEnd</b> method waits for a local process server to exit.

## Syntax

````
HRESULT WaitForProcessServerEnd(
  [in] ULONG Timeout
);
````

## Parameters

`Timeout`

Specifies how long in milliseconds to wait for a process server to exit.  If <i>Timeout</i> is INFINITE, this method will not return until a process server has ended.


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
A time-out occurred -- <i>Timeout</i> milliseconds passed without a local process server exiting.

</td>
</tr>
</table>

## Remarks

This method will only wait for the first local process server to end.  After a process server has ended, subsequent calls to this method will return immediately.

For more information about process servers and remote debugging, see <a href="https://msdn.microsoft.com/ed7ea3dc-07d1-481c-90e0-7f0b0e77ad42">Process Servers, Kernel Connection Servers, and Smart Clients</a>.

The constant INFINITE is defined in Winbase.h.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h, Winbase.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542993">EndProcessServer</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient2::WaitForProcessServerEnd method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>