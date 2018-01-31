---
UID : NF:dbgeng.IDebugControl4.ResetManagedStatus
title : IDebugControl4::ResetManagedStatus method
author : windows-driver-content
description : Clears and reinitializes the engine's managed code debugging support of the runtime debugging APIs provided by the common language runtime (CLR).
old-location : debugger\idebugcontrol4_resetmanagedstatus.htm
old-project : debugger
ms.assetid : 6A9F8963-54F2-4AD7-AB98-C3215E1F7839
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugControl4::ResetManagedStatus, IDebugControl4 interface [Windows Debugging], ResetManagedStatus method, dbgeng/IDebugControl4::ResetManagedStatus, ResetManagedStatus, debugger.idebugcontrol4_resetmanagedstatus, IDebugControl4, ResetManagedStatus method [Windows Debugging], IDebugControl4 interface, ResetManagedStatus method [Windows Debugging]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : dbgeng.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# ResetManagedStatus method
Clears and reinitializes the engine's
    managed code debugging support of the runtime debugging APIs provided by the common language runtime (CLR).

## Syntax

````
HRESULT ResetManagedStatus(
  [in] ULONG Flags
);
````

## Parameters

`Flags`

Flags for the debugging API.


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

    Managed debugging support relies on debugging
    functionality provided by the CLR.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::ResetManagedStatus method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>