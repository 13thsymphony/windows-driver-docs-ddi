---
UID: NF:dbgeng.IDebugClient5.SetOutputMask
title: IDebugClient5::SetOutputMask method
author: windows-driver-content
description: The SetOutputMask method sets the output mask for the client.
old-location: debugger\setoutputmask.htm
old-project: debugger
ms.assetid: 8fef4def-9735-4623-841b-a18995d4d403
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetOutputMask, IDebugClient2::SetOutputMask, IDebugClient5, IDebugClient_85242101-702d-4c9a-b71a-5eddd76a4fa6.xml, IDebugClient4 interface [Windows Debugging], SetOutputMask method, IDebugClient4::SetOutputMask, IDebugClient interface [Windows Debugging], SetOutputMask method, dbgeng/IDebugClient::SetOutputMask, SetOutputMask method [Windows Debugging], IDebugClient interface, SetOutputMask method [Windows Debugging], IDebugClient5 interface, SetOutputMask method [Windows Debugging], IDebugClient3 interface, IDebugClient::SetOutputMask, debugger.setoutputmask, IDebugClient2 interface [Windows Debugging], SetOutputMask method, dbgeng/IDebugClient2::SetOutputMask, dbgeng/IDebugClient3::SetOutputMask, IDebugClient2, IDebugClient3 interface [Windows Debugging], SetOutputMask method, SetOutputMask method [Windows Debugging], IDebugClient4, IDebugClient5 interface [Windows Debugging], SetOutputMask method, dbgeng/IDebugClient4::SetOutputMask, IDebugClient3, IDebugClient, IDebugClient5::SetOutputMask, IDebugClient3::SetOutputMask, dbgeng/IDebugClient5::SetOutputMask, SetOutputMask method [Windows Debugging], IDebugClient4 interface, SetOutputMask method [Windows Debugging], IDebugClient2 interface
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
-	IDebugClient.SetOutputMask
-	IDebugClient2.SetOutputMask
-	IDebugClient3.SetOutputMask
-	IDebugClient4.SetOutputMask
-	IDebugClient5.SetOutputMask
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# SetOutputMask method
The <b>SetOutputMask</b> method sets the output mask for the client.

## Syntax

````
HRESULT SetOutputMask(
  [in] ULONG Mask
);
````

## Parameters

`Mask`

Specifies the new output mask for the client.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for a description of the possible values for <i>Mask</i>.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548080">GetOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556750">SetOtherOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::SetOutputMask method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>