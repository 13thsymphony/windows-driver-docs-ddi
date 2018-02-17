---
UID: NF:dbgeng.IDebugBreakpoint.SetDataParameters
title: IDebugBreakpoint::SetDataParameters method
author: windows-driver-content
description: The SetDataParameters method sets the parameters for a processor breakpoint.
old-location: debugger\setdataparameters.htm
old-project: debugger
ms.assetid: 66878652-be29-479f-8e00-a9d8ab1b0db7
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetDataParameters method [Windows Debugging], IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint::SetDataParameters, IDebugBreakpoint2::SetDataParameters, IDebugBreakpoint, ComOther_250724e6-5ae3-4755-87de-3804e4e6f4ed.xml, IDebugBreakpoint2 interface [Windows Debugging], SetDataParameters method, SetDataParameters method [Windows Debugging], IDebugBreakpoint interface, IDebugBreakpoint interface [Windows Debugging], SetDataParameters method, debugger.setdataparameters, IDebugBreakpoint::SetDataParameters, SetDataParameters, dbgeng/IDebugBreakpoint2::SetDataParameters, SetDataParameters method [Windows Debugging]
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
-	IDebugBreakpoint.SetDataParameters
-	IDebugBreakpoint2.SetDataParameters
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# SetDataParameters method
The <b>SetDataParameters</b> method sets the parameters for a processor breakpoint.

## Syntax

````
HRESULT SetDataParameters(
  [in] ULONG Size,
  [in] ULONG AccessType
);
````

## Parameters

`Size`

The size, in bytes, of the memory block whose access triggers the breakpoint.  For more information about restrictions on the value of <i>Size</i> based on the processor type, see <a href="https://msdn.microsoft.com/ed702f01-2a30-4ffb-a804-167cf3b19936">Valid Parameters for Processor Breakpoints</a>.

`AccessType`

The type of access that triggers the breakpoint. For a list of possible value, see <a href="https://msdn.microsoft.com/ed702f01-2a30-4ffb-a804-167cf3b19936">Valid Parameters for Processor Breakpoints</a>.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The breakpoint is not a processor breakpoint.  For more information about the breakpoint type, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a>.

</td>
</tr>
</table>
 

This method can also return other error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

## Remarks

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |