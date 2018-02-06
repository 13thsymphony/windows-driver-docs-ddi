---
UID: NF:ks.KsEnableEvent
title: KsEnableEvent function
author: windows-driver-content
description: The KsEnableEvent function enables events requested through IOCTL_KS_ENABLE_EVENT. It responds to all event identifiers defined by the sets. This function can only be called at PASSIVE_LEVEL.
old-location: stream\ksenableevent.htm
old-project: stream
ms.assetid: 2338e583-4491-492e-b7e6-fa4e23485c22
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsEnableEvent, ksfunc_f6611298-cc8d-40eb-86e6-1287caff3ec0.xml, KsEnableEvent function [Streaming Media Devices], KsEnableEvent, stream.ksenableevent
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
-	KsEnableEvent
product: Windows
targetos: Windows
req.typenames: 
---


# KsEnableEvent function
The <b>KsEnableEvent</b> function enables events requested through IOCTL_KS_ENABLE_EVENT. It responds to all event identifiers defined by the sets. This function can only be called at PASSIVE_LEVEL.

## Syntax

````
NTSTATUS KsEnableEvent(
  _In_           PIRP              Irp,
  _In_           ULONG             EventSetsCount,
  _In_     const KSEVENT_SET       *EventSet,
  _Inout_        PLIST_ENTRY       EventsList,
  _In_opt_       KSEVENTS_LOCKTYPE EventsFlags,
  _In_opt_       PVOID             EventsLock
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

`EventsFlags`

Specifies <a href="..\ks\ne-ks-ksevents_locktype.md">KSEVENTS_LOCKTYPE</a> flags specifying the type of exclusion lock to be used in accessing the event list, if any. If no flag is set, then no lock is taken. If a handler is specified already, this parameter is ignored.

`EventsLock`

If the KSEVENT_SET.AddHandler for the event set containing the event being enabled is <b>NULL</b>, then this is used to synchronize access to the list. This value can be <b>NULL</b> if no flag is set in <i>EventsFlags</i>.


## Return Value

The <b>KsEnableEvent</b> function returns STATUS_SUCCESS if successful, or an error specific to the event being enabled if unsuccessful. The function always sets the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP to zero. It does not set the IO_STATUS_BLOCK.Status field, nor does it complete the IRP.

## Remarks

Minidrivers do not call <b>KsEnableEvent</b>. Only a pure KS driver or a class driver should call this routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="..\ks\nf-ks-ksdisableevent.md">KsDisableEvent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsEnableEvent function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>