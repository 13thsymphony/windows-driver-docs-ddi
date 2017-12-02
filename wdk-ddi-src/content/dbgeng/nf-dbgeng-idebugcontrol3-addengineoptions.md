---
UID: NF.dbgeng.IDebugControl3.AddEngineOptions
title: IDebugControl3::AddEngineOptions
author: windows-driver-content
description: The AddEngineOptions method turns on some of the debugger engine's options.
old-location: debugger\addengineoptions.htm
old-project: debugger
ms.assetid: 088036f5-13cb-47ba-953c-a71c923f028e
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugControl3, AddEngineOptions, IDebugControl3::AddEngineOptions
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
req.alt-api: IDebugControl.AddEngineOptions,IDebugControl2.AddEngineOptions,IDebugControl3.AddEngineOptions
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
req.iface: IDebugControl3
---

# IDebugControl3::AddEngineOptions method



## -description
<p>The <b>AddEngineOptions</b> method turns on some of the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a>'s options.</p>


## -syntax

````
HRESULT AddEngineOptions(
  [in] ULONG Options
);
````


## -parameters
<dl>

### -param Options [in]

<dd>
<p>Specifies engine options to turn on.  <i>Options</i> is a bit-set that will be combined with the existing engine options using the bitwise-OR operator.  For a description of the engine options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541475">DEBUG_ENGOPT_XXX</a>.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p>

## -remarks
<p>After the engine options have been changed, the engine sends out notification to each client's <a href="debugger.e#event_callback_objects#event_callback_objects">event callback object</a> by passing the DEBUG_CES_ENGINE_OPTIONS flag to the <a href="debugger.idebugeventcallbacks_changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> method.</p>

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
<a href="debugger.getengineoptions">GetEngineOptions</a>
</dt>
<dt>
<a href="debugger.removeengineoptions">RemoveEngineOptions</a>
</dt>
<dt>
<a href="debugger.setengineoptions">SetEngineOptions</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::AddEngineOptions method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
