---
UID: NN:dbgeng.IDebugOutputCallbacksWide
title: IDebugOutputCallbacksWide
author: windows-driver-content
description: IDebugOutputCallbacksWide interface
old-location: debugger\idebugoutputcallbackswide.htm
old-project: debugger
ms.assetid: 2f0c10f7-009a-4108-ad23-d6b6e2e1257e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDebugOutputCallbacksWide, IDebugOutputCallbacksWide interface [Windows Debugging], IDebugOutputCallbacksWide interface [Windows Debugging], described, dbgeng/IDebugOutputCallbacksWide, debugger.idebugoutputcallbackswide
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
-	IDebugOutputCallbacksWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugOutputCallbacksWide interface



## Methods

<p>The <b>IDebugOutputCallbacksWide</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [IDebugOutputCallbacksWide::Output](nf-dbgeng-idebugoutputcallbackswide-output.md) | The Output callback method is called by the engine to send output from the client to the IDebugOutputCallbacksWide object that is registered with the client. |


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugOutputCallbacksWide interface%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>