---
UID: NF:dbgeng.IDebugClient4.GetOutputMask
title: IDebugClient4::GetOutputMask method
author: windows-driver-content
description: The GetOutputMask method returns the output mask currently set for the client.
old-location: debugger\getoutputmask.htm
old-project: Debugger
ms.assetid: b1076b17-9175-4823-abb7-1c864670e8d5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugClient4, dbgeng/IDebugClient4::GetOutputMask, GetOutputMask method [Windows Debugging], IDebugClient interface, IDebugClient4::GetOutputMask, GetOutputMask, debugger.getoutputmask, IDebugClient3::GetOutputMask, dbgeng/IDebugClient2::GetOutputMask, IDebugClient::GetOutputMask, IDebugClient5 interface [Windows Debugging], GetOutputMask method, GetOutputMask method [Windows Debugging], GetOutputMask method [Windows Debugging], IDebugClient2 interface, dbgeng/IDebugClient3::GetOutputMask, GetOutputMask method [Windows Debugging], IDebugClient5 interface, IDebugClient interface [Windows Debugging], GetOutputMask method, GetOutputMask method [Windows Debugging], IDebugClient4 interface, IDebugClient, IDebugClient2::GetOutputMask, GetOutputMask method [Windows Debugging], IDebugClient3 interface, dbgeng/IDebugClient5::GetOutputMask, IDebugClient5::GetOutputMask, IDebugClient_ff2626fe-2299-4008-b655-0b7dbd46ef8b.xml, IDebugClient2 interface [Windows Debugging], GetOutputMask method, IDebugClient3 interface [Windows Debugging], GetOutputMask method, IDebugClient4 interface [Windows Debugging], GetOutputMask method, IDebugClient2, IDebugClient3, dbgeng/IDebugClient::GetOutputMask
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
-	IDebugClient.GetOutputMask
-	IDebugClient2.GetOutputMask
-	IDebugClient3.GetOutputMask
-	IDebugClient4.GetOutputMask
-	IDebugClient5.GetOutputMask
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetOutputMask method
The <b>GetOutputMask</b> method returns the output mask currently set for the client.

## Syntax

````
HRESULT GetOutputMask(
  [out] PULONG Mask
);
````

## Parameters

`Mask`

Receives the output mask for the client.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for details on how to interpret this value.


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

For an overview of output in the debugger engine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556756">SetOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548066">GetOtherOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient::GetOutputMask method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>