---
UID: NN.dbgeng.IDebugClient5
title: IDebugClient5
author: windows-driver-content
description: IDebugClient5 interface
old-location: debugger\idebugclient5.htm
old-project: debugger
ms.assetid: 4230fbc2-524a-44b1-a090-011e334629a7
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: DebugCreateEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugClient5,IDebugClient5.GetOutputLinePrefixWide,IDebugClient5.SetOutputLinePrefixWide,IDebugClient5.PushOutputLinePrefix,IDebugClient5.PushOutputLinePrefixWide,IDebugClient5.PopOutputLinePrefix,IDebugClient5.GetQuitLockString,IDebugClient5.SetQuitLockString,IDebugClient5.GetQuitLockStringWide,IDebugClient5.SetQuitLockStringWide
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

# IDebugClient5 interface



## -description

## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugClient5</b> interface inherits from <a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>. <b>IDebugClient5</b> also has these types of members:

The <b>IDebugClient5</b> interface has these methods.

Connects the debugger engine to a kernel target.

Connects to a process server.

Executes the given command to create a new process. (ANSI version)

Executes the given command to create a new process. (Unicode version)

Creates a process from a specified command line, then attach to that process or another user-mode process. (ANSI version)

Creates a process from a specified command line, then attach to that process or another user-mode process. (Unicode version)

Returns the event callbacks object registered with this client.

Returns a string describing the computer and user this client represents.

Returns the connection options for the current kernel target.

Returns the  number of event callbacks that are interested in the given events.

Returns the number of input callbacks registered over all clients.

Returns the number of output callbacks registered over all clients.

Returns the output callbacks object registered with the client.







Formats and outputs a string describing the computer and user this client represents.

Lists the servers running on a given computer.







Registers an event callbacks object with this client.

Updates some of the connection options for a live kernel target.

Registers an output callbacks object with this client.







Starts a process server.

Starts a debugging server.

 

## -members
The <b>IDebugClient5</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.attachkernelwide">AttachKernelWide</a>
</td>
<td align="left" width="63%">
Connects the debugger engine to a kernel target.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.connectprocessserverwide">ConnectProcessServerWide</a>
</td>
<td align="left" width="63%">
Connects to a process server.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.createprocess2">CreateProcess2</a>
</td>
<td align="left" width="63%">
Executes the given command to create a new process. (ANSI version)
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.createprocess2wide">CreateProcess2Wide</a>
</td>
<td align="left" width="63%">
Executes the given command to create a new process. (Unicode version)
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.createprocessandattach2">CreateProcessAndAttach2</a>
</td>
<td align="left" width="63%">
Creates a process from a specified command line, then attach to that process or another user-mode process. (ANSI version)
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.createprocessandattach2wide">CreateProcessAndAttach2Wide</a>
</td>
<td align="left" width="63%">
Creates a process from a specified command line, then attach to that process or another user-mode process. (Unicode version)
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.geteventcallbackswide">GetEventCallbacksWide</a>
</td>
<td align="left" width="63%">
Returns the event callbacks object registered with this client.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getidentitywide">GetIdentityWide</a>
</td>
<td align="left" width="63%">
Returns a string describing the computer and user this client represents.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getkernelconnectionoptionswide">GetKernelConnectionOptionsWide</a>
</td>
<td align="left" width="63%">
Returns the connection options for the current kernel target.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getnumbereventcallbacks">GetNumberEventCallbacks</a>
</td>
<td align="left" width="63%">
Returns the  number of event callbacks that are interested in the given events.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getnumberinputcallbacks">GetNumberInputCallbacks</a>
</td>
<td align="left" width="63%">
Returns the number of input callbacks registered over all clients.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getnumberoutputcallbacks">GetNumberOutputCallbacks</a>
</td>
<td align="left" width="63%">
Returns the number of output callbacks registered over all clients.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getoutputcallbackswide">GetOutputCallbacksWide</a>
</td>
<td align="left" width="63%">
Returns the output callbacks object registered with the client.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetOutputLinePrefixWide</b></td>
<td align="left" width="63%">

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetQuitLockString</b></td>
<td align="left" width="63%">

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetQuitLockStringWide</b></td>
<td align="left" width="63%">

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.outputidentitywide">OutputIdentityWide</a>
</td>
<td align="left" width="63%">
Formats and outputs a string describing the computer and user this client represents.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.outputserverswide">OutputServersWide</a>
</td>
<td align="left" width="63%">
Lists the servers running on a given computer.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>PopOutputLinePrefix</b></td>
<td align="left" width="63%">

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>PushOutputLinePrefix</b></td>
<td align="left" width="63%">

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>PushOutputLinePrefixWide</b></td>
<td align="left" width="63%">

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.seteventcallbackswide">SetEventCallbacksWide</a>
</td>
<td align="left" width="63%">
Registers an event callbacks object with this client.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setkernelconnectionoptionswide">SetKernelConnectionOptionsWide</a>
</td>
<td align="left" width="63%">
Updates some of the connection options for a live kernel target.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setoutputcallbackswide">SetOutputCallbacksWide</a>
</td>
<td align="left" width="63%">
Registers an output callbacks object with this client.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetOutputLinePrefixWide</b></td>
<td align="left" width="63%">

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetQuitLockString</b></td>
<td align="left" width="63%">

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetQuitLockStringWide</b></td>
<td align="left" width="63%">

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.startprocessserverwide">StartProcessServerWide</a>
</td>
<td align="left" width="63%">
Starts a process server.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.startserverwide">StartServerWide</a>
</td>
<td align="left" width="63%">
Starts a debugging server.
</td>
</tr>
</table>Connects the debugger engine to a kernel target.

Connects to a process server.

Executes the given command to create a new process. (ANSI version)

Executes the given command to create a new process. (Unicode version)

Creates a process from a specified command line, then attach to that process or another user-mode process. (ANSI version)

Creates a process from a specified command line, then attach to that process or another user-mode process. (Unicode version)

Returns the event callbacks object registered with this client.

Returns a string describing the computer and user this client represents.

Returns the connection options for the current kernel target.

Returns the  number of event callbacks that are interested in the given events.

Returns the number of input callbacks registered over all clients.

Returns the number of output callbacks registered over all clients.

Returns the output callbacks object registered with the client.







Formats and outputs a string describing the computer and user this client represents.

Lists the servers running on a given computer.







Registers an event callbacks object with this client.

Updates some of the connection options for a live kernel target.

Registers an output callbacks object with this client.







Starts a process server.

Starts a debugging server.

 

## -remarks


## -requirements
<table>
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
<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5 interface%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
