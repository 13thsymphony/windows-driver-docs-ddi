---
UID: NS:ksmedia.KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION
title: KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION
author: windows-driver-content
description: The KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure appends a buffer base address, a requested buffer size, and a notification count to a KSPROPERTY structure.
old-location: audio\ksrtaudio_buffer_property_with_notification.htm
old-project: audio
ms.assetid: 767c18e3-4455-4d2b-a71a-23ca11f718c8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PKSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, PKSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure pointer [Audio Devices], ksmedia/PKSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, aud-prop_43dd73ce-1c4d-4138-a7c1-9f1f17da5643.xml, *PKSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure [Audio Devices], ksmedia/KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, audio.ksrtaudio_buffer_property_with_notification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: "*PKSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION"
---

# KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure
The KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure appends a buffer base address, a requested buffer size, and a notification count to a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure.  This structure is used by the client to request allocation of the audio buffer via <a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>.

## Syntax
````
typedef struct {
  KSPROPERTY Property;
  PVOID      BaseAddress;
  ULONG      RequestedBufferSize;
  ULONG      NotificationCount;
} KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, *PKSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION;
````

## Members


`BaseAddress`

Specifies the buffer base address.  Unless the client specifies a base address, this parameter is set to <b>NULL</b>.

`NotificationCount`

Specifies the number of notifications per cycle of the cyclic buffer. Currently, the valid values are 1 or 2.  A value of 1 results in notification to registered notification events at the end of the cyclic buffer.  A value of 2 results in notifications at both the mid-point and the end of the cyclic buffer.

`Property`

A KSPROPERTY structure that the client initializes appropriately prior to calling KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION.

`RequestedBufferSize`

Specifies the buffer size in bytes.  The driver returns the actual size of the allocated buffer in the <a href="..\ksmedia\ns-ksmedia-ksrtaudio_buffer.md">KSRTAUDIO_BUFFER</a> structure that it returns.

## Remarks
The KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION request uses the KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure to describe the cyclic buffer that the client requests.  The driver returns a KSRTAUDIO_BUFFER structure to describe the buffer actually allocated.

As with KSPROPERTY_RTAUDIO_BUFFER, the value that the client writes into the <b>RequestedBufferSize</b> member is not binding on the driver.

Using KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION facilitates event signaling as DMA progresses through the cyclic buffer.  <a href="https://msdn.microsoft.com/library/windows/hardware/ff537385">KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT</a> is used to register events to receive these notifications and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537387">KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</a> is used to unregister events.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later Windows operating systems. Available in Windows Vista and later Windows operating systems. |
| **Header** | ksmedia.h |

## See Also

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537387">KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537385">KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>