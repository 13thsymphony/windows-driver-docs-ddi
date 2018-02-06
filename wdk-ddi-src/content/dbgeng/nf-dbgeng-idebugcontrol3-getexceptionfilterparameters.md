---
UID: NF:dbgeng.IDebugControl3.GetExceptionFilterParameters
title: IDebugControl3::GetExceptionFilterParameters method
author: windows-driver-content
description: The GetExceptionFilterParameters method returns the parameters for exception filters specified by exception codes or by index.
old-location: debugger\getexceptionfilterparameters.htm
old-project: debugger
ms.assetid: 6c3db06a-0305-480f-ab7f-38e4295ebe9b
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugControl3::GetExceptionFilterParameters, GetExceptionFilterParameters method [Windows Debugging], IDebugControl3 interface, IDebugControl_012d902c-ff4c-4ac8-9a35-b6cdcd1e2894.xml, debugger.getexceptionfilterparameters, dbgeng/IDebugControl2::GetExceptionFilterParameters, IDebugControl3, dbgeng/IDebugControl::GetExceptionFilterParameters, IDebugControl2 interface [Windows Debugging], GetExceptionFilterParameters method, IDebugControl3::GetExceptionFilterParameters, GetExceptionFilterParameters, IDebugControl::GetExceptionFilterParameters, IDebugControl3 interface [Windows Debugging], GetExceptionFilterParameters method, IDebugControl2::GetExceptionFilterParameters, IDebugControl interface [Windows Debugging], GetExceptionFilterParameters method, GetExceptionFilterParameters method [Windows Debugging], GetExceptionFilterParameters method [Windows Debugging], IDebugControl interface, GetExceptionFilterParameters method [Windows Debugging], IDebugControl2 interface
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
-	IDebugControl.GetExceptionFilterParameters
-	IDebugControl2.GetExceptionFilterParameters
-	IDebugControl3.GetExceptionFilterParameters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetExceptionFilterParameters method
The <b>GetExceptionFilterParameters</b> method returns the parameters for exception filters specified by exception codes or by index.

## Syntax

````
HRESULT GetExceptionFilterParameters(
  [in]           ULONG                              Count,
  [in, optional] PULONG                             Codes,
  [in]           ULONG                              Start,
  [out]          PDEBUG_EXCEPTION_FILTER_PARAMETERS Params
);
````

## Parameters

`Count`

Specifies the number of exception filters for which to return parameters.

`Codes`

Specifies an array of exception codes.  The parameters for the exception filters with these exception codes will be returned.  If <i>Codes</i> is <b>NULL</b>, <i>Start</i> is used instead.

`Start`

Specifies the index of the first exception filter.  The parameters for the exception filters starting at <i>Start</i> will be returned.  If <i>Codes</i> is not <b>NULL</b>, <i>Start</i> is ignored.

`Params`

Receives the parameters for the exception filters specified by <i>Codes</i> or <i>Start</i>.  <i>Params</i> is an array of elements of type <a href="..\dbgeng\ns-dbgeng-_debug_exception_filter_parameters.md">DEBUG_EXCEPTION_FILTER_PARAMETERS</a>.


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
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548398">GetSpecificFilterParameters</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556683">SetExceptionFilterParameters</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetExceptionFilterParameters method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>