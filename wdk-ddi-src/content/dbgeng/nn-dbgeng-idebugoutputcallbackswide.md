---
UID: NN.dbgeng.IDebugOutputCallbacksWide
title: IDebugOutputCallbacksWide
author: windows-driver-content
description: IDebugOutputCallbacksWide interface
old-location: debugger\idebugoutputcallbackswide.htm
old-project: debugger
ms.assetid: 2f0c10f7-009a-4108-ad23-d6b6e2e1257e
ms.author: windowsdriverdev
ms.date: 12/8/2017
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
req.alt-api: IDebugOutputCallbacksWide
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

# IDebugOutputCallbacksWide interface



## -description

## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugOutputCallbacksWide</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IDebugOutputCallbacksWide</b> also has these types of members:

The <b>IDebugOutputCallbacksWide</b> interface has these methods.

This method is called by the engine to send output from the client to the <b>IDebugOutputCallbacksWide</b> object that is registered with the client.

 


## -members
The <b>IDebugOutputCallbacksWide</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.idebugoutputcallbackswide_output">Output</a>
</td>
<td align="left" width="63%">
This method is called by the engine to send output from the client to the <b>IDebugOutputCallbacksWide</b> object that is registered with the client.

</td>
</tr>
</table>This method is called by the engine to send output from the client to the <b>IDebugOutputCallbacksWide</b> object that is registered with the client.

 


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
<a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugOutputCallbacksWide interface%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

