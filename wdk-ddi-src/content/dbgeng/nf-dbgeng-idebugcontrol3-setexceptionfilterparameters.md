---
UID: NF:dbgeng.IDebugControl3.SetExceptionFilterParameters
title: IDebugControl3::SetExceptionFilterParameters method
author: windows-driver-content
description: The SetExceptionFilterParameters method changes the break status and handling status for some exception filters.
old-location: debugger\setexceptionfilterparameters.htm
old-project: debugger
ms.assetid: b749f96d-d04a-48f2-9012-b7c853e0de14
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetExceptionFilterParameters method [Windows Debugging], IDebugControl2 interface, IDebugControl::SetExceptionFilterParameters, IDebugControl3 interface [Windows Debugging], SetExceptionFilterParameters method, IDebugControl interface [Windows Debugging], SetExceptionFilterParameters method, SetExceptionFilterParameters method [Windows Debugging], IDebugControl interface, IDebugControl2 interface [Windows Debugging], SetExceptionFilterParameters method, dbgeng/IDebugControl3::SetExceptionFilterParameters, dbgeng/IDebugControl2::SetExceptionFilterParameters, IDebugControl3, SetExceptionFilterParameters, SetExceptionFilterParameters method [Windows Debugging], IDebugControl3 interface, dbgeng/IDebugControl::SetExceptionFilterParameters, IDebugControl3::SetExceptionFilterParameters, debugger.setexceptionfilterparameters, SetExceptionFilterParameters method [Windows Debugging], IDebugControl_4e60bce4-e40d-46b6-83ad-55559b97fbad.xml, IDebugControl2::SetExceptionFilterParameters
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
-	IDebugControl.SetExceptionFilterParameters
-	IDebugControl2.SetExceptionFilterParameters
-	IDebugControl3.SetExceptionFilterParameters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# SetExceptionFilterParameters method
The <b>SetExceptionFilterParameters</b> method changes the <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">break status</a> and <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">handling status</a> for some exception filters.

## Syntax

````
HRESULT SetExceptionFilterParameters(
  [in] ULONG                              Count,
  [in] PDEBUG_EXCEPTION_FILTER_PARAMETERS Params
);
````

## Parameters

`Count`

Specifies the number of exception filters to change the parameters for.

`Params`

Specifies an array of exception filter parameters of type <a href="..\dbgeng\ns-dbgeng-_debug_exception_filter_parameters.md">DEBUG_EXCEPTION_FILTER_PARAMETERS</a>.  Only the <b>ExecutionOption</b>, <b>ContinueOption</b>, and <b>ExceptionCode</b> fields of these parameters are used.  The <b>ExceptionCode</b> field is used to identify the <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a> whose exception filter will be changed.  <b>ExceptionOption</b> specifies the new break status and <b>ContinueOption</b> specifies the new handling status.

If the value of the <b>ExceptionOption</b> field is DEBUG_FILTER_REMOVE and the exception filter is an arbitrary exception filter, the exception filter will be removed.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The maximum number of arbitrary exception filters 

has been exceeded.

</td>
</tr>
</table>

## Remarks

For each of the exception filter parameters in <i>Params</i>, if the exception, identified by exception code, already has a filter (specific or arbitrary), that filter will be changed.  Otherwise, a new arbitrary exception filter will be added for the exception.

For more information about <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556795">SetSpecificFilterParameters</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546650">GetExceptionFilterParameters</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::SetExceptionFilterParameters method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>