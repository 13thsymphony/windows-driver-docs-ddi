---
UID: NF:dbgeng.IDebugClient2.SetOtherOutputMask
title: IDebugClient2::SetOtherOutputMask method
author: windows-driver-content
description: The SetOtherOutputMask method sets the output mask for another client.
old-location: debugger\setotheroutputmask.htm
old-project: debugger
ms.assetid: 09e698cb-09f0-40e0-90ac-0a03c4e5c17b
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient2::SetOtherOutputMask, SetOtherOutputMask method [Windows Debugging], IDebugClient5 interface, IDebugClient, IDebugClient_73639f3d-f638-472e-9f30-e33de9321b29.xml, IDebugClient::SetOtherOutputMask, dbgeng/IDebugClient3::SetOtherOutputMask, IDebugClient3 interface [Windows Debugging], SetOtherOutputMask method, dbgeng/IDebugClient::SetOtherOutputMask, dbgeng/IDebugClient4::SetOtherOutputMask, dbgeng/IDebugClient5::SetOtherOutputMask, SetOtherOutputMask method [Windows Debugging], IDebugClient4 interface, SetOtherOutputMask method [Windows Debugging], IDebugClient2 interface, SetOtherOutputMask method [Windows Debugging], IDebugClient interface, IDebugClient2, IDebugClient5::SetOtherOutputMask, IDebugClient4::SetOtherOutputMask, dbgeng/IDebugClient2::SetOtherOutputMask, IDebugClient3::SetOtherOutputMask, IDebugClient interface [Windows Debugging], SetOtherOutputMask method, IDebugClient2 interface [Windows Debugging], SetOtherOutputMask method, IDebugClient4 interface [Windows Debugging], SetOtherOutputMask method, SetOtherOutputMask method [Windows Debugging], debugger.setotheroutputmask, SetOtherOutputMask method [Windows Debugging], IDebugClient3 interface, IDebugClient5 interface [Windows Debugging], SetOtherOutputMask method, SetOtherOutputMask
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
-	IDebugClient.SetOtherOutputMask
-	IDebugClient2.SetOtherOutputMask
-	IDebugClient3.SetOtherOutputMask
-	IDebugClient4.SetOtherOutputMask
-	IDebugClient5.SetOtherOutputMask
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# SetOtherOutputMask method
The <b>SetOtherOutputMask</b> method sets the output mask for another client.

## Syntax

````
HRESULT SetOtherOutputMask(
  [in] PDEBUG_CLIENT Client,
  [in] ULONG         Mask
);
````

## Parameters

`Client`

Specifies the client whose output mask will be set.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556756">SetOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548066">GetOtherOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::SetOtherOutputMask method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>