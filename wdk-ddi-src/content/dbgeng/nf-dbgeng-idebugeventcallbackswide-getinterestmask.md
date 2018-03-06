---
UID: NF:dbgeng.IDebugEventCallbacksWide.GetInterestMask
title: IDebugEventCallbacksWide::GetInterestMask method
author: windows-driver-content
description: The GetInterestMask callback method is called to determine which events the IDebugEventCallbacksWide object is interested in. The engine calls GetInterestMask when the object is registered with a client by using SetEventCallbacks.
old-location: debugger\idebugeventcallbackswide_getinterestmask.htm
old-project: debugger
ms.assetid: b1e62ae3-4a3d-42db-b7fe-87d1a7e0b438
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetInterestMask method [Windows Debugging], GetInterestMask method [Windows Debugging], IDebugEventCallbacksWide interface, GetInterestMask,IDebugEventCallbacksWide.GetInterestMask, IDebugEventCallbacksWide, IDebugEventCallbacksWide interface [Windows Debugging], GetInterestMask method, IDebugEventCallbacksWide::GetInterestMask, dbgeng/IDebugEventCallbacksWide::GetInterestMask, debugger.idebugeventcallbackswide_getinterestmask
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
-	IDebugEventCallbacksWide.GetInterestMask
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetInterestMask method
The <b>GetInterestMask</b> callback method is called to determine which <a href="https://msdn.microsoft.com/library/windows/hardware/ff543067">events</a> the <b>IDebugEventCallbacksWide</b> object is interested in.  The engine calls <b>GetInterestMask</b> when the object is registered with a client by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff556671">SetEventCallbacks</a>.

## Syntax

````
HRESULT GetInterestMask(
  [out] PULONG Mask
);
````

## Parameters

`Mask`

Receives a bitmask that indicates which events the object is interested in.  The engine will call only those methods that correspond to the bit flags set by <b>GetInterestMask</b>.  For a description of the bit flags and their corresponding methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541478">DEBUG_EVENT_XXX</a>.


## Return Value

The return value S_OK indicates the method was successful.  All other return values indicate an error occurred,  in which case the <b>SetEventCallbacks</b> call will fail and the callback object will not be used nor will it receive events.

## Remarks

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |