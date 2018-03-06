---
UID: NC:hdaudio.PREGISTER_NOTIFICATION_EVENT
title: PREGISTER_NOTIFICATION_EVENT
author: windows-driver-content
description: The RegisterNotificationEvent routine registers a kernel event so that it can receive DMA progress notifications.The function pointer type for a RegisterNotificationEvent routine is defined as follows.
old-location: audio\registernotificationevent.htm
old-project: audio
ms.assetid: 44702d79-80ac-411f-ae47-bf60b9cb541d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PREGISTER_NOTIFICATION_EVENT, RegisterNotificationEvent, RegisterNotificationEvent callback function [Audio Devices], aud-prop2_fa7a1f01-c553-40df-971b-932f8da48353.xml, audio.registernotificationevent, hdaudio/RegisterNotificationEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Hdaudio.h
api_name:
-	RegisterNotificationEvent
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---


# PREGISTER_NOTIFICATION_EVENT callback function
The <i>RegisterNotificationEvent</i> routine registers a kernel event so that it can receive DMA progress notifications.

The function pointer type for a <i>RegisterNotificationEvent</i> routine is defined as follows.

## Syntax

```
PREGISTER_NOTIFICATION_EVENT PregisterNotificationEvent;

NTSTATUS PregisterNotificationEvent(
  PVOID _context,
  HANDLE Handle,
  PKEVENT NotificationEvent
)
{...}
```

## Parameters

`_context`

Specifies the context value from the Context member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a> structure.

`Handle`

Handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>.

`NotificationEvent`

A pointer to a kernel event that must be notified as DMA progresses.  Depending on the notification count parameter that is used with <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer_with_notification.md">AllocateDmaBufferWithNotification</a>, the registered event is signaled one or two times for every time that the DMA passes through the audio buffer.


## Return Value

<i>RegisterNotificationEvent</i> returns STATUS_SUCCESS if the call successfully registers the event. Otherwise, the routine returns STATUS_INSUFFICIENT_RESOURCES to indicate that there are insufficient resources that are available to complete the operation.

## Remarks

<i>RegisterNotificationEvent</i> registers a kernel event with the HD Audio bus driver.  The HD Audio bus driver maintains a list of registered notification events for each DMA engine, and signals them every time that the engine receives an IOC interrupt.  Events are unregistered by using <a href="..\hdaudio\nc-hdaudio-punregister_notification_event.md">UnregisterNotificationEvent</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows.  |
| **Target Platform** | Desktop |
| **Header** | hdaudio.h (include Hdaudio.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\hdaudio\nc-hdaudio-punregister_notification_event.md">UnregisterNotificationEvent</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer_with_notification.md">AllocateDmaBufferWithNotification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PREGISTER_NOTIFICATION_EVENT callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>