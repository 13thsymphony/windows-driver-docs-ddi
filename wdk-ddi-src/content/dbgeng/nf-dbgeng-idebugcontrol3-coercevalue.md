---
UID: NF:dbgeng.IDebugControl3.CoerceValue
title: IDebugControl3::CoerceValue method
author: windows-driver-content
description: The CoerceValue method converts a value of one type into a value of another type.
old-location: debugger\coercevalue.htm
old-project: debugger
ms.assetid: db037fc8-d503-4a72-b6bc-d5189f6786d4
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: CoerceValue method [Windows Debugging], CoerceValue method [Windows Debugging], IDebugControl interface, CoerceValue method [Windows Debugging], IDebugControl2 interface, CoerceValue method [Windows Debugging], IDebugControl3 interface, CoerceValue,IDebugControl3.CoerceValue, IDebugControl interface [Windows Debugging], CoerceValue method, IDebugControl2 interface [Windows Debugging], CoerceValue method, IDebugControl2::CoerceValue, IDebugControl3, IDebugControl3 interface [Windows Debugging], CoerceValue method, IDebugControl3::CoerceValue, IDebugControl::CoerceValue, IDebugControl_034a690e-25bb-40a1-b788-7b148ba0d9cd.xml, dbgeng/IDebugControl2::CoerceValue, dbgeng/IDebugControl3::CoerceValue, dbgeng/IDebugControl::CoerceValue, debugger.coercevalue
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
-	Dbgeng.h
api_name:
-	IDebugControl.CoerceValue
-	IDebugControl2.CoerceValue
-	IDebugControl3.CoerceValue
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugControl3::CoerceValue method
The <b>CoerceValue</b> method converts a value of one type into a value of another type.

## Syntax

```
HRESULT CoerceValue(
  PDEBUG_VALUE In,
  ULONG        OutType,
  PDEBUG_VALUE Out
);
```

## Parameters

`In`

Specifies the value to be converted

`OutType`

Specifies the desired type for the converted value. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541719">DEBUG_VALUE</a> for possible values.

`Out`

Receives the converted value.  The type of this value will be the type specified by <i>OutType</i>.


## Return Value

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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

This method converts a value of one type into a value of another type.  If the specified <i>OutType</i> is not capable of containing the information supplied by the <i>In</i> variable, data will be lost.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541719">DEBUG_VALUE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>