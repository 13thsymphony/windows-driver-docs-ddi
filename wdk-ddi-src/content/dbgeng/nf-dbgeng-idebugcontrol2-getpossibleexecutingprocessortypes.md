---
UID: NF:dbgeng.IDebugControl2.GetPossibleExecutingProcessorTypes
title: IDebugControl2::GetPossibleExecutingProcessorTypes method
author: windows-driver-content
description: The GetPossibleExecutingProcessorTypes method returns the processor types that are supported by the computer running the current target.
old-location: debugger\getpossibleexecutingprocessortypes.htm
old-project: debugger
ms.assetid: fb11b655-2528-447f-9f5e-3c9e4e040156
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetPossibleExecutingProcessorTypes method [Windows Debugging], GetPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl interface, GetPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl2 interface, GetPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl3 interface, GetPossibleExecutingProcessorTypes,IDebugControl2.GetPossibleExecutingProcessorTypes, IDebugControl interface [Windows Debugging], GetPossibleExecutingProcessorTypes method, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetPossibleExecutingProcessorTypes method, IDebugControl2::GetPossibleExecutingProcessorTypes, IDebugControl3 interface [Windows Debugging], GetPossibleExecutingProcessorTypes method, IDebugControl3::GetPossibleExecutingProcessorTypes, IDebugControl::GetPossibleExecutingProcessorTypes, IDebugControl_582811e7-4eb0-4b94-a5d0-8c903ea8c2fe.xml, dbgeng/IDebugControl2::GetPossibleExecutingProcessorTypes, dbgeng/IDebugControl3::GetPossibleExecutingProcessorTypes, dbgeng/IDebugControl::GetPossibleExecutingProcessorTypes, debugger.getpossibleexecutingprocessortypes
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


# IDebugControl2::GetPossibleExecutingProcessorTypes method
The <b>GetPossibleExecutingProcessorTypes</b> method returns the processor types that are supported by the computer running the current target.

## Syntax

```
HRESULT GetPossibleExecutingProcessorTypes(
  ULONG  Start,
  ULONG  Count,
  PULONG Types
);
```

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547939">GetNumberPossibleExecutingProcessorTypes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>