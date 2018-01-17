---
UID: NF:portcls.IMiniportWaveRTStreamNotification.UnregisterNotificationEvent
title: IMiniportWaveRTStreamNotification::UnregisterNotificationEvent method
author: windows-driver-content
description: The UnregisterNotificationEvent method unregisters an event from DMA driven event notification.
old-location: audio\iminiportwavertstreamnotification_unregisternotificationevent.htm
old-project: audio
ms.assetid: 5b264784-7680-4c3b-9fc7-0609c53b53a2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportWaveRTStreamNotification, IMiniportWaveRTStreamNotification::UnregisterNotificationEvent, UnregisterNotificationEvent
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
req.alt-api: IMiniportWaveRTStreamNotification.UnregisterNotificationEvent
req.alt-loc: portcls.h
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
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IMiniportWaveRTStreamNotification::UnregisterNotificationEvent method



## -description
The <code>UnregisterNotificationEvent</code> method unregisters an event from DMA driven event notification.



## -syntax

````
NTSTATUS UnregisterNotificationEvent(
  [in] PKEVENT NotificationEvent
);
````


## -parameters

### -param NotificationEvent [in]

A pointer to a previously registered kernel event (PKEVENT) to be unregistered from notification as DMA progresses.


## -returns
<code>UnregisterNotificationEvent</code> returns a status value of STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.


## -remarks
The port driver calls this method in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537387">KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</a> property request from a client.  The port driver maps the user-mode event handle to a kernel event pointer and passes the pointer in with the <i>NotificationEvent</i> parameter.


## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iminiportwavertstreamnotification.md">IMiniportWaveRTStreamNotification</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537387">KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveRTStreamNotification::UnregisterNotificationEvent method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

