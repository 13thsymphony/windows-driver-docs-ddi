---
UID: NF:dbgeng.IDebugControl3.GetNumberPossibleExecutingProcessorTypes
title: IDebugControl3::GetNumberPossibleExecutingProcessorTypes method
author: windows-driver-content
description: The GetNumberPossibleExecutingProcessorTypes method returns the number of processor types that are supported by the computer running the current target.
old-location: debugger\getnumberpossibleexecutingprocessortypes.htm
old-project: debugger
ms.assetid: 9e4ca8a6-f33f-4403-a52f-f242ce40aac8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetNumberPossibleExecutingProcessorTypes method [Windows Debugging], GetNumberPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl interface, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl2 interface, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging], IDebugControl3 interface, GetNumberPossibleExecutingProcessorTypes,IDebugControl3.GetNumberPossibleExecutingProcessorTypes, IDebugControl interface [Windows Debugging], GetNumberPossibleExecutingProcessorTypes method, IDebugControl2 interface [Windows Debugging], GetNumberPossibleExecutingProcessorTypes method, IDebugControl2::GetNumberPossibleExecutingProcessorTypes, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetNumberPossibleExecutingProcessorTypes method, IDebugControl3::GetNumberPossibleExecutingProcessorTypes, IDebugControl::GetNumberPossibleExecutingProcessorTypes, IDebugControl_62f066c6-6ffb-4323-ad82-786a8a763783.xml, dbgeng/IDebugControl2::GetNumberPossibleExecutingProcessorTypes, dbgeng/IDebugControl3::GetNumberPossibleExecutingProcessorTypes, dbgeng/IDebugControl::GetNumberPossibleExecutingProcessorTypes, debugger.getnumberpossibleexecutingprocessortypes
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
-	IDebugControl.GetNumberPossibleExecutingProcessorTypes
-	IDebugControl2.GetNumberPossibleExecutingProcessorTypes
-	IDebugControl3.GetNumberPossibleExecutingProcessorTypes
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugControl3::GetNumberPossibleExecutingProcessorTypes method
The <b>GetNumberPossibleExecutingProcessorTypes</b> method returns the number of processor types that are supported by the computer running the current target.

## Syntax

```
HRESULT GetNumberPossibleExecutingProcessorTypes(
  PULONG Number
);
```

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

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548130">GetPossibleExecutingProcessorTypes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>