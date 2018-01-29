---
UID : NC:hdaudio.PUNREGISTER_NOTIFICATION_EVENT
title : PUNREGISTER_NOTIFICATION_EVENT
author : windows-driver-content
description : The UnregisterNotificationEvent routine deletes the registration of an event that was previously registered by a call to RegisterNotificationEvent.The function pointer type for an UnregisterNotificationEvent routine is defined as follows.
old-location : audio\unregisternotificationevent.htm
old-project : audio
ms.assetid : 525e2dd9-68e1-468d-895e-d9f57372d619
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audio.unregisternotificationevent, UnregisterNotificationEvent callback function [Audio Devices], UnregisterNotificationEvent, PUNREGISTER_NOTIFICATION_EVENT, PUNREGISTER_NOTIFICATION_EVENT, hdaudio/UnregisterNotificationEvent, aud-prop2_3f7488ae-5744-422e-871f-54dc2fd63bc2.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : hdaudio.h
req.include-header : Hdaudio.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of Windows.
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
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---


# PUNREGISTER_NOTIFICATION_EVENT callback function
The <i>UnregisterNotificationEvent</i> routine deletes the registration of an event that was previously registered by a call to <a href="..\hdaudio\nc-hdaudio-pregister_notification_event.md">RegisterNotificationEvent</a>.

The function pointer type for an <i>UnregisterNotificationEvent</i> routine is defined as follows.

## Syntax

```
PUNREGISTER_NOTIFICATION_EVENT PunregisterNotificationEvent;

NTSTATUS PunregisterNotificationEvent(
  PVOID _context,
  HANDLE Handle,
  PKEVENT NotificationEvent
)
{...}
```

## Parameters

`_context`



`Handle`



`NotificationEvent`




## Return Value

<i>UnregisterNotificationEvent</i> returns STATUS_SUCCESS if the call successfully unregisters the notification event. Otherwise, the routine returns STATUS_INVALID_PARAMETER to indicate that the specified tag is not valid.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hdaudio.h (include Hdaudio.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL. |
| **DDI compliance rules** |  |

## See Also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>

<a href="..\hdaudio\nc-hdaudio-pregister_notification_event.md">RegisterNotificationEvent</a>

<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>

<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PUNREGISTER_NOTIFICATION_EVENT callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>