---
UID: NF:dbgeng.IDebugClient5.GetNumberOutputCallbacks
title: IDebugClient5::GetNumberOutputCallbacks method
author: windows-driver-content
description: The GetNumberOutputCallbacks method returns the number of output callbacks registered over all clients.
old-location: debugger\getnumberoutputcallbacks.htm
old-project: Debugger
ms.assetid: 20bc6141-8c4a-4a98-acb3-506840893db6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GetNumberOutputCallbacks method [Windows Debugging], GetNumberOutputCallbacks method [Windows Debugging], IDebugClient5 interface, IDebugClient5, IDebugClient5 interface [Windows Debugging], GetNumberOutputCallbacks method, dbgeng/IDebugClient5::GetNumberOutputCallbacks, IDebugClient_ce6e107b-a356-434a-81d7-eccb8495289d.xml, GetNumberOutputCallbacks, IDebugClient5::GetNumberOutputCallbacks, debugger.getnumberoutputcallbacks
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
-	IDebugClient5.GetNumberOutputCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetNumberOutputCallbacks method
The <b>GetNumberOutputCallbacks</b> method returns the number of <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">output callbacks</a> registered over all clients.

## Syntax

````
HRESULT GetNumberOutputCallbacks(
  [out] PULONG Count
);
````

## Parameters

`Count`

Receives the number of output callbacks that have been registered.


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

Each client can have at most one output callback registered with it.

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556751">SetOutputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547923">GetNumberInputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556751">SetOutputCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547896">GetNumberEventCallbacks</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient5::GetNumberOutputCallbacks method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>