---
UID: NF:ks.KsEnableEventWithAllocator
title: KsEnableEventWithAllocator function
author: windows-driver-content
description: The KsEnableEventWithAllocator function enables events requested through IOCTL_KS_ENABLE_EVENT but also allows an optional allocator callback to be used to provide a buffer for the parameters.
old-location: stream\ksenableeventwithallocator.htm
old-project: stream
ms.assetid: ec017e5c-1c26-426d-935f-7a554d3db915
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsEnableEventWithAllocator function [Streaming Media Devices], ks/KsEnableEventWithAllocator, stream.ksenableeventwithallocator, KsEnableEventWithAllocator, ksfunc_2af8f81f-ef1d-4ad5-9267-dfdc14005183.xml
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
-	KsEnableEventWithAllocator
product: Windows
targetos: Windows
req.typenames: 
---


# KsEnableEventWithAllocator function
The <b>KsEnableEventWithAllocator</b> function enables events requested through IOCTL_KS_ENABLE_EVENT but also allows an optional allocator callback to be used to provide a buffer for the parameters. It responds to all event identifiers defined by the sets. This function can only be called at PASSIVE_LEVEL.

If used, the filter may need to free the buffer in some nonconventional manner. Note that the IRP_BUFFERED_IO and IRP_DEALLOCATE_BUFFER flags are not set when using a custom allocator.

## Syntax

````
NTSTATUS KsEnableEventWithAllocator(
  _In_           PIRP              Irp,
  _In_           ULONG             EventSetsCount,
  _In_     const KSEVENT_SET       *EventSet,
  _Inout_        PLIST_ENTRY       EventsList,
  _In_opt_       KSEVENTS_LOCKTYPE EventsFlags,
  _In_opt_       PVOID             EventsLock,
  _In_opt_       PFNKSALLOCATOR    Allocator,
  _In_opt_       ULONG             EventItemSize
);
````

## Parameters

`Irp`

Specifies the IRP with the enable request being handled. The file object associated with the IRP is stored with the event for later comparison when disabling the event.

`EventSetsCount`

Indicates the number of event set structures being passed.

`EventSet`

Specifies a pointer to the list of event set information.

`EventsList`

If the enabling event's KSEVENT_SET.AddHandler for the event set is <b>NULL</b>, it must point to the head of the list of KSEVENT_ENTRY items on which the event is to be added. This function assumes a single list for at least a subset of events.

`OPTIONAL`

TBD

`EventsLock`

If the KSEVENT_SET.AddHandler for the event set containing the event being enabled is <b>NULL</b>, then this is used to synchronize access to the list. This value can be <b>NULL</b> if no flag is set in <i>EventsFlags</i>.

`Allocator`

Optionally points to an allocation function that will be used to allocate memory to store the event parameters.

`EventItemSize`

Optionally contains the size of each KSEVENT_ITEM structure in each list of events. The event item may be extended in order to store private information. If this parameter is zero, the structure size is assumed to be normal. If it is greater than or equal to an event item structure, the KSEVENT_ITEM_IRP_STORAGE macro can be used to return a pointer to the event item so the custom data can be retrieved. On 64-bit platforms, this parameter must be a multiple of 8.


## Return Value

Same as <b>KsEnableEvent</b>, which returns STATUS_SUCCESS if successful, or an error specific to the event being enabled if unsuccessful. The function always sets the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP to zero. It does not set the IO_STATUS_BLOCK.Status field, nor does it complete the IRP.

## Remarks

If the optional allocator callback is used, the filter may need to free the buffer in some nonconventional manner. Note that the IRP_BUFFERED_IO and IRP_DEALLOCATE_BUFFER flags are not set when using a custom allocator.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |