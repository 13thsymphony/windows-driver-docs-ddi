---
UID: NL:dbgeng.DebugBaseEventCallbacks
title: DebugBaseEventCallbacks
author: windows-driver-content
description: The DebugBaseEventCallbacks class provides a base implementation of the IDebugEventCallbacks interface.
old-location: debugger\debugbaseeventcallbacks.htm
old-project: debugger
ms.assetid: B0422248-2F5F-4AE6-93C9-D96B5E4A1B5A
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: DebugBaseEventCallbacks, DebugBaseEventCallbacks class [Windows Debugging], DebugBaseEventCallbacks class [Windows Debugging], described, dbgeng/DebugBaseEventCallbacks, debugger.debugbaseeventcallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: class
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
req.lib: 
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
-	DebugBaseEventCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# DebugBaseEventCallbacks Class
The <b>DebugBaseEventCallbacks</b> class provides a base implementation
of the <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> interface.  

A program can derive an event callbacks class from <b>DebugBaseEventCallbacks</b> and implement
only the methods needed. 

Be careful to implement <a href="https://msdn.microsoft.com/165c83cb-c0be-4a09-9220-a5208f660308">GetInterestMask</a> appropriately.

## Methods

<p>The <b>DebugBaseEventCallbacks</b> class has these methods.</p>

| Method | Description |
| ---- |:---- |


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a>



<a href="https://msdn.microsoft.com/165c83cb-c0be-4a09-9220-a5208f660308">GetInterestMask</a>