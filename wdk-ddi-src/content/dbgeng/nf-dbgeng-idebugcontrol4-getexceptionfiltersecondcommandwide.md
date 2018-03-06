---
UID: NF:dbgeng.IDebugControl4.GetExceptionFilterSecondCommandWide
title: IDebugControl4::GetExceptionFilterSecondCommandWide method
author: windows-driver-content
description: The GetExceptionFilterSecondCommandWide method returns the command that will be executed by the debugger engine upon the second chance of a specified exception.
old-location: debugger\getexceptionfiltersecondcommandwide.htm
old-project: debugger
ms.assetid: 17a61847-78b7-45b8-b02b-3ba4cdba6bff
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetExceptionFilterSecondCommandWide method [Windows Debugging], GetExceptionFilterSecondCommandWide method [Windows Debugging], IDebugControl4 interface, GetExceptionFilterSecondCommandWide,IDebugControl4.GetExceptionFilterSecondCommandWide, IDebugControl4, IDebugControl4 interface [Windows Debugging], GetExceptionFilterSecondCommandWide method, IDebugControl4::GetExceptionFilterSecondCommandWide, dbgeng/IDebugControl4::GetExceptionFilterSecondCommandWide, debugger.getexceptionfiltersecondcommandwide
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl4.GetExceptionFilterSecondCommandWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetExceptionFilterSecondCommandWide method
The <b>GetExceptionFilterSecondCommandWide</b>  method returns the command that will be executed by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> upon the second chance of a specified <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a>.

## Syntax

````
HRESULT GetExceptionFilterSecondCommandWide(
  [in]            ULONG  Index,
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG CommandSize
);
````

## Parameters

`Index`

Specifies the index of the exception filter whose second-chance command will be returned.  <i>Index</i> can also refer to the default exception filter to return the second-chance command for those exceptions that do not have a specific or arbitrary exception filter.

`Buffer`

Receives the second-chance command for the exception filter.

`BufferSize`

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.

`CommandSize`

Receives the size, in characters, of the second-chance command for the exception filter.  If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.


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

Only exception filters support a second-chance command.  If <i>Index</i> refers to a <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">specific event filter</a>, the command returned to <i>Buffer</i> will be empty.  The returned command will also be empty if no second-chance command has been set for the specified exception.

For more information about <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546611">GetEventFilterCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556687">SetExceptionFilterSecondCommand</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetExceptionFilterSecondCommandWide method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>