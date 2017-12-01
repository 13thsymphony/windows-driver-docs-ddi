---
UID: NF.dbgeng.IDebugControl6.GetSynchronizationStatus
title: IDebugControl6::GetSynchronizationStatus
author: windows-driver-content
description: The GetSynchronizationStatus method returns information about the synchronization status of the debugger engine.
old-location: debugger\idebugcontrol6_getsynchronizationstatus.htm
old-project: debugger
ms.assetid: 94DD7FBF-2D4F-4DD9-A49E-A9FA494BF995
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: IDebugControl6, GetSynchronizationStatus, IDebugControl6::GetSynchronizationStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl6.GetSynchronizationStatus
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
req.iface: IDebugControl6
---

# IDebugControl6::GetSynchronizationStatus method



## -description
<p>The GetSynchronizationStatus method returns information about the synchronization status of the debugger engine.</p>


## -syntax

````
HRESULT GetSynchronizationStatus(
  [out] PULONG SendsAttempted,
  [out] PULONG SecondsSinceLastResponse
);
````


## -parameters
<dl>

### -param <i>SendsAttempted</i> [out]

<dd>
<p>The number of packet sends that have been attempted by the current debugger-engine kernel transport mechanism. This number will be incremented if engine did not receive a packet "ACK" for the last packet sent by the engine to the target.</p>
</dd>

### -param <i>SecondsSinceLastResponse</i> [out]

<dd>
<p>The number of seconds since the last response.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="debugger.hresult_values">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful. </p>

<p> </p>

## -remarks
<p>When the client object connects to a session, the most recent output from the session is sent to the client. If the session is currently waiting on input, the client object is given the opportunity to provide input. Thus, the client object synchronizes with the session's input and output.</p>

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
<dt>Dbgeng.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558852">Synchronizing with the Target Computer</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol6.md">IDebugControl6</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl6::GetSynchronizationStatus method%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
