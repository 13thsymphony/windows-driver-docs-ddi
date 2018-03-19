---
UID: NC:ks.PFNKSADDEVENT
title: PFNKSADDEVENT
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniAddEvent routine is called when a client registers to be notified of an event. This routine is optional.
old-location: stream\avstrminiaddevent.htm
old-project: stream
ms.assetid: ff80bbc7-93b1-4319-a549-f896ce0f4611
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniAddEvent, AVStrMiniAddEvent routine [Streaming Media Devices], PFNKSADDEVENT, avstclbk_31147072-c3de-4b02-9fb1-b7f67765acc4.xml, ks/AVStrMiniAddEvent, stream.avstrminiaddevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
-	UserDefined
api_location:
-	ks.h
api_name:
-	AVStrMiniAddEvent
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# PFNKSADDEVENT callback function
An AVStream minidriver's <i>AVStrMiniAddEvent</i> routine is called when a client registers to be notified of an event. This routine is optional.

## Syntax

```
PFNKSADDEVENT Pfnksaddevent;

NTSTATUS Pfnksaddevent(
  PIRP Irp,
  PKSEVENTDATA EventData,
  _KSEVENT_ENTRY *EventEntry
)
{...}
```

## Parameters

`Irp`

Specifies the IRP describing the event add request.

`EventData`

Pointer to a <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure describing the notification method for this event.

`*EventEntry`

Pointer to an AVStream-generated <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> structure describing how the event is triggered.


## Return Value

<i>AVStrMiniAddEvent</i> should return STATUS_SUCCESS or an error specific to the event being enabled.

## Remarks

If you do not provide an add event handler, AVStream adds the event to the object list. See <a href="https://msdn.microsoft.com/7add2055-8d3f-432d-8aa1-44459ac197dd">Event Handling in AVStream</a>.

Frequently this callback implements vendor-specific behavior and then calls <a href="..\ks\nf-ks-ksfilteraddevent.md">KsFilterAddEvent</a> or <a href="..\ks\nf-ks-kspinaddevent.md">KsPinAddEvent</a>. The minidriver passes the <i>EventEntry</i> pointer received here in calls to <i>KsFilterAddEvent</i> or <i>KsPinAddEvent</i>.

The minidriver specifies this routine's address in the <b>AddHandler</b> member of a <a href="..\ks\ns-ks-ksevent_item.md">KSEVENT_ITEM</a> structure. <a href="https://msdn.microsoft.com/7add2055-8d3f-432d-8aa1-44459ac197dd">Event Handling in AVStream</a> describes how the minidriver provides this structure to the class driver.

If an AVStream minidriver specifies <b>AddHandler</b> as non-NULL, AVStream does not add the item to the object's event list. If minidriver specifies an <b>AddHandler</b> and does not add the event to the object's event list through <b>KsDefaultAddEventHandler()</b> or a <b>Ks*AddEvent </b>call, the minidriver is responsible for cleaning up the event.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-ksevent_item.md">KSEVENT_ITEM</a>



<a href="..\ks\nf-ks-kspingenerateevents.md">KsPinGenerateEvents</a>



<a href="..\ks\nf-ks-ksfilteraddevent.md">KsFilterAddEvent</a>



<a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a>



<a href="..\ks\ns-ks-ksautomation_table_.md">KSAUTOMATION_TABLE</a>



<a href="..\ks\nf-ks-kspinaddevent.md">KsPinAddEvent</a>



<a href="..\ks\nc-ks-pfnksremoveevent.md">AVStrMiniRemoveEvent</a>



<a href="..\ks\nf-ks-ksfiltergenerateevents.md">KsFilterGenerateEvents</a>



<a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a>