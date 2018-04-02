---
UID: NF:dbgeng.IDebugControl.SetEffectiveProcessorType
title: IDebugControl::SetEffectiveProcessorType method
author: windows-driver-content
description: The SetEffectiveProcessorType method sets the effective processor type of the processor of the computer that is running the target.
old-location: debugger\seteffectiveprocessortype.htm
old-project: debugger
ms.assetid: 7c524181-c438-47ae-9180-1b0c623f24dc
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugControl, IDebugControl interface [Windows Debugging], SetEffectiveProcessorType method, IDebugControl2 interface [Windows Debugging], SetEffectiveProcessorType method, IDebugControl2::SetEffectiveProcessorType, IDebugControl3 interface [Windows Debugging], SetEffectiveProcessorType method, IDebugControl3::SetEffectiveProcessorType, IDebugControl::SetEffectiveProcessorType, IDebugControl_284f54f4-897e-4329-b588-5eae0c638179.xml, SetEffectiveProcessorType method [Windows Debugging], SetEffectiveProcessorType method [Windows Debugging], IDebugControl interface, SetEffectiveProcessorType method [Windows Debugging], IDebugControl2 interface, SetEffectiveProcessorType method [Windows Debugging], IDebugControl3 interface, SetEffectiveProcessorType,IDebugControl.SetEffectiveProcessorType, dbgeng/IDebugControl2::SetEffectiveProcessorType, dbgeng/IDebugControl3::SetEffectiveProcessorType, dbgeng/IDebugControl::SetEffectiveProcessorType, debugger.seteffectiveprocessortype
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
-	IDebugControl.SetEffectiveProcessorType
-	IDebugControl2.SetEffectiveProcessorType
-	IDebugControl3.SetEffectiveProcessorType
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugControl::SetEffectiveProcessorType method
The <b>SetEffectiveProcessorType</b> method sets the effective processor type of the processor of the computer that is running the target.

## Syntax

```
HRESULT SetEffectiveProcessorType(
  ULONG Type
);
```

## Parameters

`Type`

Specifies the type of the processor.  For possible values, see the <i>Type</i> parameter in <a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546595">GetEffectiveProcessorType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>