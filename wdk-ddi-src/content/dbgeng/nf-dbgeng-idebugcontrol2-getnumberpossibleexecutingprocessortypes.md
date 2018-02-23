---
UID: NF:dbgeng.IDebugControl2.GetNumberPossibleExecutingProcessorTypes
title: IDebugControl2::GetNumberPossibleExecutingProcessorTypes method
author: windows-driver-content
description: The GetNumberPossibleExecutingProcessorTypes method returns the number of processor types that are supported by the computer running the current target.
old-location: debugger\getnumberpossibleexecutingprocessortypes.htm
old-project: Debugger
ms.assetid: 9e4ca8a6-f33f-4403-a52f-f242ce40aac8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugControl2::GetNumberPossibleExecutingProcessorTypes, IDebugControl, dbgeng/IDebugControl3::GetNumberPossibleExecutingProcessorTypes, GetNumberPossibleExecutingProcessorTypes, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl_62f066c6-6ffb-4323-ad82-786a8a763783.xml, IDebugControl2, dbgeng/IDebugControl::GetNumberPossibleExecutingProcessorTypes, dbgeng/IDebugControl2::GetNumberPossibleExecutingProcessorTypes, IDebugControl::GetNumberPossibleExecutingProcessorTypes, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl3 interface, debugger.getnumberpossibleexecutingprocessortypes, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl2 interface, IDebugControl2 interface [Windows Debugging], GetNumberPossibleExecutingProcessorTypes method, IDebugControl3 interface [Windows Debugging], GetNumberPossibleExecutingProcessorTypes method, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl interface, IDebugControl interface [Windows Debugging], GetNumberPossibleExecutingProcessorTypes method, IDebugControl3::GetNumberPossibleExecutingProcessorTypes
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
-	IDebugControl.GetNumberPossibleExecutingProcessorTypes
-	IDebugControl2.GetNumberPossibleExecutingProcessorTypes
-	IDebugControl3.GetNumberPossibleExecutingProcessorTypes
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetNumberPossibleExecutingProcessorTypes method
The <b>GetNumberPossibleExecutingProcessorTypes</b> method returns the number of processor types that are supported by the computer running the current target.

## Syntax

````
HRESULT GetNumberPossibleExecutingProcessorTypes(
  [out] PULONG Number
);
````

## Parameters

`Number`

Receives the number of processor types.


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



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548130">GetPossibleExecutingProcessorTypes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl::GetNumberPossibleExecutingProcessorTypes method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>