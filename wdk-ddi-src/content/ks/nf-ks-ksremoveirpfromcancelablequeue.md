---
UID: NF:ks.KsRemoveIrpFromCancelableQueue
title: KsRemoveIrpFromCancelableQueue function
author: windows-driver-content
description: The KsRemoveIrpFromCancelableQueue function pops the next noncanceled IRP from the specified queue that can be canceled and removes its cancel status.
old-location: stream\ksremoveirpfromcancelablequeue.htm
old-project: stream
ms.assetid: 6bc23364-07c9-4a01-b475-e4620f62a674
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsRemoveIrpFromCancelableQueue, KsRemoveIrpFromCancelableQueue function [Streaming Media Devices], ks/KsRemoveIrpFromCancelableQueue, ksfunc_35dd895b-1a0b-40a2-bc84-cdc2844bd30f.xml, stream.ksremoveirpfromcancelablequeue
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsRemoveIrpFromCancelableQueue
product: Windows
targetos: Windows
req.typenames: 
---


# KsRemoveIrpFromCancelableQueue function
The <b>KsRemoveIrpFromCancelableQueue</b> function pops the next noncanceled IRP from the specified queue that can be canceled and removes its cancel status. The function searches the list until an IRP is found that has a cancel routine or until the end of the list is reached. The function minimizes the use of the cancel spin lock by using the provided spin lock to synchronize access in most cases. The function may be called at IRQ level DISPATCH_LEVEL or lower.

## Syntax

````
PIRP KsRemoveIrpFromCancelableQueue(
  _Inout_ PLIST_ENTRY             QueueHead,
  _In_    PKSPIN_LOCK             SpinLock,
  _In_    KSLIST_ENTRY_LOCATION   ListLocation,
  _In_    KSIRP_REMOVAL_OPERATION RemovalOperation
);
````

## Parameters

`QueueHead`

Points to the head of the queue from which to remove the IRP.

`SpinLock`

Points to driver's spin lock for queue access.

`ListLocation`

Indicates whether this IRP should come from the beginning or end of the queue.

`RemovalOperation`

Specifies whether the IRP is removed from the list or just acquired by setting the cancel function to <b>NULL</b>. If it is only acquired, the IRP must be later released with <b>KsReleaseIrpOnCancelableQueue</b> or completely removed with <b>KsRemoveSpecificIrpFromCancelableQueue</b>.


## Return Value

The <b>KsRemoveIrpFromCancelableQueue</b> function returns the next noncanceled IRP on the list, or it returns <b>NULL</b> if none is found or if an IRP that has not already been acquired cannot be found.

## Remarks

These enumerations are used in the previous parameters to control where the IRP is removed from and how.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef enum {
    KsListEntryTail,
    KsListEntryHead
} KSLIST_ENTRY_LOCATION;

typedef enum {
    KsAcquireOnly,
    KsAcquireAndRemove
} KSIRP_REMOVAL_OPERATION;
 </pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="..\ks\nf-ks-ksreleaseirponcancelablequeue.md">KsReleaseIrpOnCancelableQueue</a>



<a href="..\ks\nf-ks-ksremovespecificirpfromcancelablequeue.md">KsRemoveSpecificIrpFromCancelableQueue</a>