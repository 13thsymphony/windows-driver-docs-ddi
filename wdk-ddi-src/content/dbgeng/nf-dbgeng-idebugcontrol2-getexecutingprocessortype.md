---
UID: NF:dbgeng.IDebugControl2.GetExecutingProcessorType
title: IDebugControl2::GetExecutingProcessorType method
author: windows-driver-content
description: The GetExecutingProcessorType method returns the executing processor type for the processor for which the last event occurred.
old-location: debugger\getexecutingprocessortype.htm
old-project: debugger
ms.assetid: 62d0397b-da20-414e-accf-656749a771f6
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetExecutingProcessorType method [Windows Debugging], IDebugControl interface, IDebugControl3 interface [Windows Debugging], GetExecutingProcessorType method, dbgeng/IDebugControl2::GetExecutingProcessorType, IDebugControl2::GetExecutingProcessorType, IDebugControl2 interface [Windows Debugging], GetExecutingProcessorType method, dbgeng/IDebugControl3::GetExecutingProcessorType, IDebugControl::GetExecutingProcessorType, GetExecutingProcessorType method [Windows Debugging], dbgeng/IDebugControl::GetExecutingProcessorType, IDebugControl interface [Windows Debugging], GetExecutingProcessorType method, IDebugControl2, IDebugControl_b2aad495-5a68-4888-bedb-da76edbfbe7a.xml, debugger.getexecutingprocessortype, IDebugControl, GetExecutingProcessorType method [Windows Debugging], IDebugControl2 interface, GetExecutingProcessorType method [Windows Debugging], IDebugControl3 interface, IDebugControl3::GetExecutingProcessorType, GetExecutingProcessorType
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
-	IDebugControl.GetExecutingProcessorType
-	IDebugControl2.GetExecutingProcessorType
-	IDebugControl3.GetExecutingProcessorType
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetExecutingProcessorType method
The <b>GetExecutingProcessorType</b> method returns the executing processor type for the processor for which the last event occurred.

## Syntax

````
HRESULT GetExecutingProcessorType(
  [out] PULONG Type
);
````

## Parameters

`Type`

Receives the processor type.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a> for a list of possible values this parameter can receive.


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

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetExecutingProcessorType method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>