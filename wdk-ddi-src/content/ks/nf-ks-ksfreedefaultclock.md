---
UID : NF:ks.KsFreeDefaultClock
title : KsFreeDefaultClock function
author : windows-driver-content
description : The KsFreeDefaultClock function frees a default clock structure previously allocated with KsAllocateDefaultClock, taking into account any currently running timer DPCs.
old-location : stream\ksfreedefaultclock.htm
old-project : stream
ms.assetid : e2fc87c9-e48f-4e18-ae1b-52a7cc701e91
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsFreeDefaultClock, ksfunc_30a51e64-775e-4412-9a8c-b186e6caf932.xml, KsFreeDefaultClock function [Streaming Media Devices], stream.ksfreedefaultclock, ks/KsFreeDefaultClock
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---


# KsFreeDefaultClock function
The <b>KsFreeDefaultClock</b> function frees a default clock structure previously allocated with <a href="..\ks\nf-ks-ksallocatedefaultclock.md">KsAllocateDefaultClock</a>, taking into account any currently running timer DPCs. This assumes that all instances of the clock have been closed. This may actually just decrement the internal reference counter and allow a pending DPC to free the structure asynchronously.

This may only be called at PASSIVE_LEVEL.

## Syntax

````
VOID KsFreeDefaultClock(
  _In_ PKSDEFAULTCLOCK DefaultClock
);
````

## Parameters

`DefaultClock`

Specifies the previously allocated structure to free.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |