---
UID: NF:dbgeng.IDebugControl3.GetPossibleExecutingProcessorTypes
title: IDebugControl3::GetPossibleExecutingProcessorTypes method
author: windows-driver-content
description: The GetPossibleExecutingProcessorTypes method returns the processor types that are supported by the computer running the current target.
old-location: debugger\getpossibleexecutingprocessortypes.htm
old-project: debugger
ms.assetid: fb11b655-2528-447f-9f5e-3c9e4e040156
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetPossibleExecutingProcessorTypes method [Windows Debugging], GetPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl interface, GetPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl2 interface, GetPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl3 interface, GetPossibleExecutingProcessorTypes,IDebugControl3.GetPossibleExecutingProcessorTypes, IDebugControl interface [Windows Debugging], GetPossibleExecutingProcessorTypes method, IDebugControl2 interface [Windows Debugging], GetPossibleExecutingProcessorTypes method, IDebugControl2::GetPossibleExecutingProcessorTypes, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetPossibleExecutingProcessorTypes method, IDebugControl3::GetPossibleExecutingProcessorTypes, IDebugControl::GetPossibleExecutingProcessorTypes, IDebugControl_582811e7-4eb0-4b94-a5d0-8c903ea8c2fe.xml, dbgeng/IDebugControl2::GetPossibleExecutingProcessorTypes, dbgeng/IDebugControl3::GetPossibleExecutingProcessorTypes, dbgeng/IDebugControl::GetPossibleExecutingProcessorTypes, debugger.getpossibleexecutingprocessortypes
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
-	IDebugControl.GetPossibleExecutingProcessorTypes
-	IDebugControl2.GetPossibleExecutingProcessorTypes
-	IDebugControl3.GetPossibleExecutingProcessorTypes
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetPossibleExecutingProcessorTypes method
The <b>GetPossibleExecutingProcessorTypes</b> method returns the processor types that are supported by the computer running the current target.

## Syntax

````
HRESULT GetPossibleExecutingProcessorTypes(
  [in]  ULONG  Start,
  [in]  ULONG  Count,
  [out] PULONG Types
);
````

## Parameters

`Start`

Specifies the index of the first processor type to return.  The processor types are indexed by numbers zero through to the number of processor types supported by the current target minus one.  The number of processor types supported by the current target can be found using <a href="https://msdn.microsoft.com/library/windows/hardware/ff547939">GetNumberPossibleExecutingProcessorTypes</a>.

`Count`

Specifies how many processor types to return.

`Types`

Receives the list of processor types.  The number of elements this array holds is <i>Count</i>.  For a description of the processor types see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>.


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

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547939">GetNumberPossibleExecutingProcessorTypes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetPossibleExecutingProcessorTypes method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>