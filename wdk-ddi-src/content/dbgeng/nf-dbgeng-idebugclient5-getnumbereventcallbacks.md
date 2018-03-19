---
UID: NF:dbgeng.IDebugClient5.GetNumberEventCallbacks
title: IDebugClient5::GetNumberEventCallbacks method
author: windows-driver-content
description: The GetNumberEventCallbacks method returns the number of event callbacks that are interested in the given events.
old-location: debugger\getnumbereventcallbacks.htm
old-project: debugger
ms.assetid: 02001bad-bafe-432d-bc07-011cb6981ae6
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetNumberEventCallbacks method [Windows Debugging], GetNumberEventCallbacks method [Windows Debugging], IDebugClient5 interface, GetNumberEventCallbacks,IDebugClient5.GetNumberEventCallbacks, IDebugClient5, IDebugClient5 interface [Windows Debugging], GetNumberEventCallbacks method, IDebugClient5::GetNumberEventCallbacks, IDebugClient_976101a5-6218-475a-b8e9-e7091e2524d6.xml, dbgeng/IDebugClient5::GetNumberEventCallbacks, debugger.getnumbereventcallbacks
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient5.GetNumberEventCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetNumberEventCallbacks method
The <b>GetNumberEventCallbacks</b> method returns the number of event callbacks that are interested in the given <a href="https://msdn.microsoft.com/library/windows/hardware/ff543067">events</a>.

## Syntax

````
HRESULT GetNumberEventCallbacks(
  [in]  ULONG  EventFlags,
  [out] PULONG Count
);
````

## Parameters

`EventFlags`

Specifies a set of events used to filter out some of the event callbacks; only event callbacks that have indicated an interest in one of the events in <i>EventFlags</i> will be counted.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541478">DEBUG_EVENT_XXX</a> for a list of the events.

`Count`

Receives the number of event callbacks that are interested in at least one of the events in <i>EventFlags</i>.


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

Each client can have at most one event callback registered with it.  When a callback is registered with a client, its <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a> method is called to allow the client to specify which events it is interested in.

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547923">GetNumberInputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556671">SetEventCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546601">GetEventCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547931">GetNumberOutputCallbacks</a>