---
UID : NF:dbgeng.IDebugBreakpoint2.GetDataParameters
title : IDebugBreakpoint2::GetDataParameters method
author : windows-driver-content
description : The GetDataParameters method returns the parameters for a processor breakpoint.
old-location : debugger\getdataparameters.htm
old-project : debugger
ms.assetid : e281c67a-df97-464e-9996-b15c18172dc4
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : dbgeng/IDebugBreakpoint::GetDataParameters, debugger.getdataparameters, GetDataParameters, IDebugBreakpoint interface [Windows Debugging], GetDataParameters method, GetDataParameters method [Windows Debugging], IDebugBreakpoint2 interface, IDebugBreakpoint2 interface [Windows Debugging], GetDataParameters method, ComOther_297fe316-4a1a-476b-a804-056bb56b6e77.xml, IDebugBreakpoint::GetDataParameters, GetDataParameters method [Windows Debugging], dbgeng/IDebugBreakpoint2::GetDataParameters, GetDataParameters method [Windows Debugging], IDebugBreakpoint interface, IDebugBreakpoint2::GetDataParameters, IDebugBreakpoint2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
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
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetDataParameters method
The <b>GetDataParameters</b> method returns the parameters for a processor breakpoint.

## Syntax

````
HRESULT GetDataParameters(
  [out] PULONG Size,
  [out] PULONG AccessType
);
````

## Parameters

`Size`

The size, in bytes, of the memory block whose access triggers the breakpoint.  For more information about restrictions on the value of <i>Size</i> based on the processor type, see <a href="https://msdn.microsoft.com/ed702f01-2a30-4ffb-a804-167cf3b19936">Valid Parameters for Processor Breakpoints</a>.

`AccessType`

The type of access that triggers the breakpoint.  For a list of possible values, see <a href="https://msdn.microsoft.com/ed702f01-2a30-4ffb-a804-167cf3b19936">Valid Parameters for Processor Breakpoints</a>.


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

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the information that is returned in <i>Size</i> and <i>AccessType</i>.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |