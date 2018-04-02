---
UID: NF:dbgeng.IDebugSystemObjects4.SetCurrentSystemId
title: IDebugSystemObjects4::SetCurrentSystemId method
author: windows-driver-content
description: The SetCurrentSystemId method makes the specified target the current target.
old-location: debugger\setcurrentsystemid.htm
old-project: debugger
ms.assetid: 95b761ff-ca78-4793-b5eb-a9ff35a963d3
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugSystemObjects3 interface [Windows Debugging], SetCurrentSystemId method, IDebugSystemObjects3::SetCurrentSystemId, IDebugSystemObjects4, IDebugSystemObjects4 interface [Windows Debugging], SetCurrentSystemId method, IDebugSystemObjects4::SetCurrentSystemId, IDebugSystemObjects_70a23767-a18b-4920-828a-34fe863fec4a.xml, SetCurrentSystemId method [Windows Debugging], SetCurrentSystemId method [Windows Debugging], IDebugSystemObjects3 interface, SetCurrentSystemId method [Windows Debugging], IDebugSystemObjects4 interface, SetCurrentSystemId,IDebugSystemObjects4.SetCurrentSystemId, dbgeng/IDebugSystemObjects3::SetCurrentSystemId, dbgeng/IDebugSystemObjects4::SetCurrentSystemId, debugger.setcurrentsystemid
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
-	IDebugSystemObjects3.SetCurrentSystemId
-	IDebugSystemObjects4.SetCurrentSystemId
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSystemObjects4::SetCurrentSystemId method
The <b>SetCurrentSystemId</b> method makes the specified target the current target.

## Syntax

```
HRESULT SetCurrentSystemId(
  ULONG Id
);
```

## Parameters

`Id`

Specifies the engine target ID for the target that is to become the current target.


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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No process with the given ID was found.

</td>
</tr>
</table>

## Remarks

This method also sets the current thread and current process, and may change the current computer.

If the current target is changed, the callback <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> will be called with the DEBUG_CES_CURRENT_THREAD bit set.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550892">IDebugSystemObjects3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550893">IDebugSystemObjects4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>