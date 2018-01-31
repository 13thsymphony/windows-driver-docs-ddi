---
UID : NF:dbgeng.IDebugControl3.GetEventFilterText
title : IDebugControl3::GetEventFilterText method
author : windows-driver-content
description : The GetEventFilterText method returns a short description of an event for a specific filter.
old-location : debugger\geteventfiltertext.htm
old-project : debugger
ms.assetid : d311a030-e24c-427c-8a52-0c67d4fac653
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugControl3, GetEventFilterText, debugger.geteventfiltertext, dbgeng/IDebugControl2::GetEventFilterText, GetEventFilterText method [Windows Debugging], IDebugControl3 interface, IDebugControl2 interface [Windows Debugging], GetEventFilterText method, IDebugControl3::GetEventFilterText, IDebugControl::GetEventFilterText, GetEventFilterText method [Windows Debugging], IDebugControl2 interface, IDebugControl2::GetEventFilterText, GetEventFilterText method [Windows Debugging], GetEventFilterText method [Windows Debugging], IDebugControl interface, dbgeng/IDebugControl::GetEventFilterText, IDebugControl3 interface [Windows Debugging], GetEventFilterText method, dbgeng/IDebugControl3::GetEventFilterText, IDebugControl_61936aac-8fe2-4f18-86aa-cba1404d845f.xml, IDebugControl interface [Windows Debugging], GetEventFilterText method
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
req.typenames : DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetEventFilterText method
The <b>GetEventFilterText</b>  method returns a short description of an event for a specific filter.

## Syntax

````
HRESULT GetEventFilterText(
  [in]            ULONG  Index,
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG TextSize
);
````

## Parameters

`Index`

Specifies the index of the event filter whose description will be returned.  Only the specific filters have a description attached to them; <i>Index</i> must refer to a specific filter.

`Buffer`

Receives the description of the specific filter.

`BufferSize`

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.

`TextSize`

Receives the size of the event description.  If <i>TextSize</i> is <b>NULL</b>, this information is not returned.


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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
<i>Index</i> did not refer to a specific filter.  This can occur if <i>Index</i> refers to an arbitrary exception filter.

</td>
</tr>
</table>

## Remarks

For more information about <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.

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

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548398">GetSpecificFilterParameters</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetEventFilterText method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>