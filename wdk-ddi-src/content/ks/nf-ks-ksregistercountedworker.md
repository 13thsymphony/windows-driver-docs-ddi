---
UID : NF:ks.KsRegisterCountedWorker
title : KsRegisterCountedWorker function
author : windows-driver-content
description : Handles clients registering for use of a thread.
old-location : stream\ksregistercountedworker.htm
old-project : stream
ms.assetid : acec8050-44bd-4082-9875-d504135e1b9f
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ks/KsRegisterCountedWorker, KsRegisterCountedWorker, ksfunc_2d4b1740-9b91-420d-81be-a56034445893.xml, KsRegisterCountedWorker function [Streaming Media Devices], stream.ksregistercountedworker
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


# KsRegisterCountedWorker function
Handles clients registering for use of a thread.

## Syntax

````
NTSTATUS KsRegisterCountedWorker(
  _In_  WORK_QUEUE_TYPE  WorkQueueType,
  _In_  PWORK_QUEUE_ITEM CountedWorkItem,
  _Out_ PKSWORKER        *Worker
);
````

## Parameters

`WorkQueueType`

Contains the priority of the work thread. This is normally one of the following: CriticalWorkQueue, DelayedWorkQueue, or HyperCriticalWorkQueue.

`CountedWorkItem`

Contains a pointer to the work queue item that will be queued as needed based on the current count value.

`Worker`

Contains the opaque context that must be used when scheduling a work item. Also contains the queue type, and is used to synchronize completion of work items.


## Return Value

Returns STATUS_SUCCESS if a worker was initialized.

## Remarks

This must be matched by a corresponding <a href="..\ks\nf-ks-ksunregisterworker.md">KsUnregisterWorker</a> when thread use is completed. This function resembles <a href="..\ks\nf-ks-ksregisterworker.md">KsRegisterWorker</a>, with the addition of passing the work item that will always be queued. This is to be used with <a href="..\ks\nf-ks-ksincrementcountedworker.md">KsIncrementCountedWorker</a> and <a href="..\ks\nf-ks-ksdecrementcountedworker.md">KsDecrementCountedWorker</a> in order to minimize the number of work items queued, and reduce mutual exclusion code necessary in a work item needed to serialize access against multiple work item threads. The worker queue can still be used to queue other work items. This may only be called at PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |