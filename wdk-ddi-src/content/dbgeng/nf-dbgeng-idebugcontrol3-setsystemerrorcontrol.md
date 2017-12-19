---
UID: NF.dbgeng.IDebugControl3.SetSystemErrorControl
title: IDebugControl3::SetSystemErrorControl method
author: windows-driver-content
description: The SetSystemErrorControl method sets the control values for handling system errors.
old-location: debugger\setsystemerrorcontrol.htm
old-project: Debugger
ms.assetid: 0ff15743-29df-44dc-a18b-ba8f7e49058e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugControl3, IDebugControl3::SetSystemErrorControl, SetSystemErrorControl
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
req.alt-api: IDebugControl.SetSystemErrorControl,IDebugControl2.SetSystemErrorControl,IDebugControl3.SetSystemErrorControl
req.alt-loc: dbgeng.h
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
---

# IDebugControl3::SetSystemErrorControl method



## -description
The <b>SetSystemErrorControl</b> method sets the control values for handling system errors.



## -syntax

````
HRESULT SetSystemErrorControl(
  [in] ULONG OutputLevel,
  [in] ULONG BreakLevel
);
````


## -parameters

### -param OutputLevel [in]

Specifies the level at which system errors are printed to the engine's output.  If the level of the system error is less than or equal to <i>OutputLevel</i>, the error is printed to the debugger console.


### -param BreakLevel [in]

Specifies the level at which system errors break into the debugger.  If the level of the system error is less than or equal to <i>BreakLevel</i>, the error breaks into the debugger.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
The level of a system error can take one of the following three values, listed from lowest to highest: SLE_ERROR, SLE_MINORERROR, and SLE_WARNING.  These values are defined in Winuser.h.

When a system error occurs, the engine calls the <a href="debugger.idebugeventcallbacks_systemerror">IDebugEventCallbacks::SystemError</a> method of the event callbacks.  If the level is less than or equal to the <i>BreakLevel</i> parameter, the error will break into the debugger.  If the level is greater than <i>BreakLevel</i>, the engine will proceed with execution in the target as indicated by the <b>IDebugEventCallbacks::SystemError</b> method calls.  For more information about how the engine proceeds after an event, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.


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
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="debugger.getsystemerrorcontrol">GetSystemErrorControl</a>
</dt>
<dt>
<a href="debugger.idebugeventcallbacks_systemerror">IDebugEventCallbacks::SystemError</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl::SetSystemErrorControl method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

