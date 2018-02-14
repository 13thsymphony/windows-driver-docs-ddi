---
UID: NF:ks.KsSetTargetState
title: KsSetTargetState function
author: windows-driver-content
description: Sets the enabled state of a target device associated with the specified object header.
old-location: stream\kssettargetstate.htm
old-project: stream
ms.assetid: 36f14936-8cc6-4488-aa0f-343e4fbb84e3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksfunc_7e05a5c0-2c82-4b20-a199-3955c61c6e40.xml, stream.kssettargetstate, ks/KsSetTargetState, KsSetTargetState function [Streaming Media Devices], KsSetTargetState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsSetTargetState
product: Windows
targetos: Windows
req.typenames: 
---


# KsSetTargetState function
Sets the enabled state of a target device associated with the specified object header.

## Syntax

````
VOID KsSetTargetState(
  _In_ KSOBJECT_HEADER Header,
  _In_ KSTARGET_STATE  TargetState
);
````

## Parameters

`Header`

Points to a header previously allocated by <a href="..\ks\nf-ks-ksallocatedeviceheader.md">KsAllocateDeviceHeader</a>.

`TargetState`

Contains the new state of the target associated with this object header. This may be either KSTARGET_STATE_DISABLED or KSTARGET_STATE_ENABLED.


## Return Value

None.

## Remarks

Assumes that such a target has been set with <a href="..\ks\nf-ks-kssettargetdeviceobject.md">KsSetTargetDeviceObject</a>. The target is initially disabled, and is ignored when recalculating stack depth. For WDM Streaming devices, this is called on a transition back to a Stop state, after having enabled the target and used <a href="..\ks\nf-ks-ksrecalculatestackdepth.md">KsRecalculateStackDepth</a> on a transition to Acquire state. This allows the stack depth to be minimized.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |