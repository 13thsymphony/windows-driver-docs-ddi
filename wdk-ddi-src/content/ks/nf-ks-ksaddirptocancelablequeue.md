---
UID : NF:ks.KsAddIrpToCancelableQueue
title : KsAddIrpToCancelableQueue function
author : windows-driver-content
description : The KsAddIrpToCancelableQueue function adds an IRP to a queue of cancelable IRPs, thus allowing the IRP to be canceled. If the IRP had been previously set to a canceled state, the KsAddIrpToCancelableQueue function completes the canceling of that IRP.
old-location : stream\ksaddirptocancelablequeue.htm
old-project : stream
ms.assetid : 399ca0d6-6355-40f8-ac2c-c69d7ae699e1
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsAddIrpToCancelableQueue, ks/KsAddIrpToCancelableQueue, ksfunc_8a3caaa5-29ca-4c55-a3f6-8214808954b3.xml, stream.ksaddirptocancelablequeue, KsAddIrpToCancelableQueue function [Streaming Media Devices]
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


# KsAddIrpToCancelableQueue function
The <b>KsAddIrpToCancelableQueue</b> function adds an IRP to a queue of cancelable IRPs, thus allowing the IRP to be canceled. If the IRP had been previously set to a canceled state, the <b>KsAddIrpToCancelableQueue </b>function completes the canceling of that IRP.

## Syntax

````
VOID KsAddIrpToCancelableQueue(
  _Inout_  PLIST_ENTRY           QueueHead,
  _In_     PKSPIN_LOCK           SpinLock,
  _In_     PIRP                  Irp,
  _In_     KSLIST_ENTRY_LOCATION ListLocation,
  _In_opt_ PDRIVER_CANCEL        DriverCancel
);
````

## Parameters

`QueueHead`

Specifies the driver-allocated storage for the head of the queue on which to add the IRP.

`SpinLock`

Points to driver's spin lock for queue access to the queue specified at <i>QueueHead</i>. A copy of this pointer is kept in the IRP's KSQUEUE_SPINLOCK_IRP_STORAGE(Irp) for use by the cancel routine, if necessary.

`Irp`

Specifies the IRP to add to the queue specified at <i>QueueHead</i>.

`ListLocation`

Indicates whether this IRP should be placed at the beginning or end of the queue. This value must be KsListEntryTail or KsListEntryHead.

`DriverCancel`

Optional parameter that specifies a driver-supplied cancel routine to use. If this is <b>NULL</b>, the standard <a href="https://msdn.microsoft.com/library/windows/hardware/ff561011">KsCancelRoutine</a> is used.


## Return Value

None

## Remarks

If the IRP has been put into a cancel state when this routine is called, <b>KsAddIrpToCancelableQueue</b> will immediately call the cancel routine specified at <i>DriverCancel</i>, or if no routine was specified at <i>DriverCancel </i>the default streaming cancel routine is called.

The <b>KsAddIrpToCancelableQueue</b> function allows IRPs to be canceled even before being placed on a cancel list, or when being moved from one list to another. This function can be called at IRQ level DISPATCH_LEVEL or lower unless the driver-allocated queue and all entries in the queue are system-resident or allocated from resident storage.

The function does not use the cancel spin lock to add items to the list. Access to the list is synchronized using the provided spin lock and relies on atomic operations on Irp-&gt;CancelRoutine.

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