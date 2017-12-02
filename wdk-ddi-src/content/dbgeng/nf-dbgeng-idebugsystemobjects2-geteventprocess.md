---
UID: NF.dbgeng.IDebugSystemObjects2.GetEventProcess
title: IDebugSystemObjects2::GetEventProcess
author: windows-driver-content
description: The GetEventProcess method returns the engine process ID for the process on which the last event occurred.
old-location: debugger\geteventprocess.htm
old-project: debugger
ms.assetid: 77cf1995-f3f3-4a03-bba7-9df230a10da0
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSystemObjects2, GetEventProcess, IDebugSystemObjects2::GetEventProcess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSystemObjects.GetEventProcess,IDebugSystemObjects2.GetEventProcess,IDebugSystemObjects3.GetEventProcess,IDebugSystemObjects4.GetEventProcess
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
req.iface: IDebugSystemObjects2
---

# IDebugSystemObjects2::GetEventProcess method



## -description
<p>The <b>GetEventProcess</b> method returns the engine process ID for the process on which the last event occurred.</p>


## -syntax

````
HRESULT GetEventProcess(
  [out] PULONG Id
);
````


## -parameters
<dl>

### -param Id [out]

<dd>
<p>Receives the engine process ID.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>In kernel-mode debugging, the engine process ID for the virtual process representing the kernel is returned.</p>

<p>For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details about debugger engine events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>