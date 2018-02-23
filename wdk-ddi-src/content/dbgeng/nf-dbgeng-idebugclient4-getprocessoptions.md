---
UID: NF:dbgeng.IDebugClient4.GetProcessOptions
title: IDebugClient4::GetProcessOptions method
author: windows-driver-content
description: The GetProcessOptions method retrieves the process options affecting the current process.
old-location: debugger\getprocessoptions.htm
old-project: Debugger
ms.assetid: ff2d4da4-5a10-4196-92bd-ac4b244a2257
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugClient4, IDebugClient_5d54bc2a-5691-4a3a-b3c9-92fc577cdabb.xml, IDebugClient5 interface [Windows Debugging], GetProcessOptions method, GetProcessOptions method [Windows Debugging], IDebugClient3::GetProcessOptions, IDebugClient::GetProcessOptions, GetProcessOptions method [Windows Debugging], IDebugClient2 interface, IDebugClient2::GetProcessOptions, GetProcessOptions method [Windows Debugging], IDebugClient4 interface, GetProcessOptions method [Windows Debugging], IDebugClient5 interface, IDebugClient5::GetProcessOptions, IDebugClient2 interface [Windows Debugging], GetProcessOptions method, IDebugClient4::GetProcessOptions, GetProcessOptions method [Windows Debugging], IDebugClient interface, IDebugClient, GetProcessOptions method [Windows Debugging], IDebugClient3 interface, GetProcessOptions, dbgeng/IDebugClient2::GetProcessOptions, debugger.getprocessoptions, dbgeng/IDebugClient::GetProcessOptions, dbgeng/IDebugClient4::GetProcessOptions, IDebugClient3 interface [Windows Debugging], GetProcessOptions method, IDebugClient2, dbgeng/IDebugClient3::GetProcessOptions, dbgeng/IDebugClient5::GetProcessOptions, IDebugClient3, IDebugClient4 interface [Windows Debugging], GetProcessOptions method, IDebugClient interface [Windows Debugging], GetProcessOptions method
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
-	IDebugClient.GetProcessOptions
-	IDebugClient2.GetProcessOptions
-	IDebugClient3.GetProcessOptions
-	IDebugClient4.GetProcessOptions
-	IDebugClient5.GetProcessOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetProcessOptions method
The <b>GetProcessOptions</b> method retrieves the process options affecting the current process.

## Syntax

````
HRESULT GetProcessOptions(
  [out] PULONG Options
);
````

## Parameters

`Options`

Receives a set of flags representing the process options for the current process.  For details on these options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>.


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

This method is only available in live user-mode debugging.

Some of the process options are global options, others are specific to the current process.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537917">AddProcessOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556765">SetProcessOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554505">RemoveProcessOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient::GetProcessOptions method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>