---
UID: NF:dbgeng.IDebugControl4.AddBreakpoint2
title: IDebugControl4::AddBreakpoint2 method
author: windows-driver-content
description: The AddBreakpoint2 method creates a new breakpoint for the current target.
old-location: debugger\addbreakpoint2.htm
old-project: debugger
ms.assetid: 001a64dd-1470-42e0-98ba-22ba33f3fa69
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl4, IDebugControl4::AddBreakpoint2, AddBreakpoint2
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
req.alt-api: IDebugControl4.AddBreakpoint2
req.alt-loc: Dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl4::AddBreakpoint2 method



## -description
The <b>AddBreakpoint2</b>  method creates a new breakpoint for the current target.



## -syntax

````
HRESULT AddBreakpoint2(
  [in]  ULONG            Type,
  [in]  ULONG            DesiredId,
  [out] IDebugBreakpoint **Bp
);
````


## -parameters

### -param Type [in]

Specifies the breakpoint type of the new breakpoint.  This can be either of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_CODE

</td>
<td>
<a href="debugger.s#software_breakpoint#software_breakpoint"><i>software breakpoint</i></a>

</td>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_DATA

</td>
<td>
<a href="debugger.p#processor_breakpoint#processor_breakpoint"><i>processor breakpoint</i></a>

</td>
</tr>
</table>
 


### -param DesiredId [in]

Specifies the desired ID of the new breakpoint.  If it is DEBUG_ANY_ID, the engine will pick an unused ID.


### -param Bp [out]

Receives an interface pointer to the new breakpoint.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The breakpoint couldn't be created with the desired ID or the value of <i>Type</i> was not recognized.

 

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
If <i>DesiredId</i> is not DEBUG_ANY_ID and another breakpoint already uses the ID <i>DesiredId</i>, these methods will fail.

Breakpoints are created empty and disabled.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a> for details on configuring and enabling the breakpoint.

The client is saved as the adder of the new breakpoint. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff545576">GetAdder</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">Breakpoints</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554487">RemoveBreakpoint</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::AddBreakpoint2 method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

