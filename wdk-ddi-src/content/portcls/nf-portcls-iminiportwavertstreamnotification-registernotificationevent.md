---
UID: NF:portcls.IMiniportWaveRTStreamNotification.RegisterNotificationEvent
title: IMiniportWaveRTStreamNotification::RegisterNotificationEvent method
author: windows-driver-content
description: The RegisterNotificationEvent method registers an event to be notified for DMA-driven event notification.
old-location: audio\iminiportwavertstreamnotification_registernotificationevent.htm
old-project: audio
ms.assetid: 269eccd8-e477-4082-930b-1f4b3e3706b9
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IMiniportWaveRTStreamNotification, IMiniportWaveRTStreamNotification interface [Audio Devices], RegisterNotificationEvent method, IMiniportWaveRTStreamNotification::RegisterNotificationEvent, RegisterNotificationEvent method [Audio Devices], RegisterNotificationEvent method [Audio Devices], IMiniportWaveRTStreamNotification interface, RegisterNotificationEvent,IMiniportWaveRTStreamNotification.RegisterNotificationEvent, audio.iminiportwavertstreamnotification_registernotificationevent, audmp-routines_82613ca5-1ae2-449d-8883-2d6ee50aecf7.xml, portcls/IMiniportWaveRTStreamNotification::RegisterNotificationEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.irql: Passive level.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWaveRTStreamNotification.RegisterNotificationEvent
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IMiniportWaveRTStreamNotification::RegisterNotificationEvent method
The <code>RegisterNotificationEvent</code> method registers an event to be notified for DMA-driven event notification.

## Syntax

```
NTSTATUS RegisterNotificationEvent(
  PKEVENT NotificationEvent
);
```

## Parameters

`NotificationEvent`

A pointer to a kernel event (PKEVENT) to be registered for notification as DMA progresses.


## Return Value

<code>RegisterNotificationEvent</code> returns a status value of STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.

## Remarks

The port driver calls this method in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537385">KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT</a> property request from a client.  The port driver maps the user-mode event handle to a kernel event pointer and passes the pointer in with the <i>NotificationEvent</i> parameter.

Typically, when DMA-driven event notification is enabled, the DMA hardware is programmed to generate hardware interrupts at the intended notification points in the cyclic audio buffer.  When the driver interrupt service routine (ISR) detects this interrupt, it queues a deferred procedure call (DPC).  The DPC, in turn, signals each registered event. We recommend using a try/except construct  around the event that signals the call.

For more information about the behavior of the KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT property, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537499">KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h |
| **IRQL** | Passive level. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536739">IMiniportWaveRTStreamNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537385">KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537499">KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY</a>