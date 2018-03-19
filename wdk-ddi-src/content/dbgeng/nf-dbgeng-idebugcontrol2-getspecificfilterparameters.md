---
UID: NF:dbgeng.IDebugControl2.GetSpecificFilterParameters
title: IDebugControl2::GetSpecificFilterParameters method
author: windows-driver-content
description: The GetSpecificFilterParameters method returns the parameters for specific event filters.
old-location: debugger\getspecificfilterparameters.htm
old-project: debugger
ms.assetid: d2140270-558d-4cd9-b497-f61be40c7a87
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetSpecificFilterParameters method [Windows Debugging], GetSpecificFilterParameters method [Windows Debugging], IDebugControl interface, GetSpecificFilterParameters method [Windows Debugging], IDebugControl2 interface, GetSpecificFilterParameters method [Windows Debugging], IDebugControl3 interface, GetSpecificFilterParameters,IDebugControl2.GetSpecificFilterParameters, IDebugControl interface [Windows Debugging], GetSpecificFilterParameters method, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetSpecificFilterParameters method, IDebugControl2::GetSpecificFilterParameters, IDebugControl3 interface [Windows Debugging], GetSpecificFilterParameters method, IDebugControl3::GetSpecificFilterParameters, IDebugControl::GetSpecificFilterParameters, IDebugControl_ebe245a7-c76c-4b31-aa58-ccad250ed92a.xml, dbgeng/IDebugControl2::GetSpecificFilterParameters, dbgeng/IDebugControl3::GetSpecificFilterParameters, dbgeng/IDebugControl::GetSpecificFilterParameters, debugger.getspecificfilterparameters
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
-	IDebugControl.GetSpecificFilterParameters
-	IDebugControl2.GetSpecificFilterParameters
-	IDebugControl3.GetSpecificFilterParameters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetSpecificFilterParameters method
The <b>GetSpecificFilterParameters</b> method returns the parameters for specific event filters.

## Syntax

````
HRESULT GetSpecificFilterParameters(
  [in]  ULONG                             Start,
  [in]  ULONG                             Count,
  [out] PDEBUG_SPECIFIC_FILTER_PARAMETERS Params
);
````

## Parameters

`Start`

Specifies the index of the first specific event filter whose parameters will be returned.

`Count`

Specifies the number of specific event filters to return parameters for.

`Params`

Receives the parameters for the specific event filters.  <i>Params</i> is an array of elements of type <a href="..\dbgeng\ns-dbgeng-_debug_specific_filter_parameters.md">DEBUG_SPECIFIC_FILTER_PARAMETERS</a>.


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

For more information about <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556795">SetSpecificFilterParameters</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546650">GetExceptionFilterParameters</a>