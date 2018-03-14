---
UID: NS:wdm._TARGET_DEVICE_CUSTOM_NOTIFICATION
title: "_TARGET_DEVICE_CUSTOM_NOTIFICATION"
author: windows-driver-content
description: The TARGET_DEVICE_CUSTOM_NOTIFICATION structure describes a custom device event.
old-location: kernel\target_device_custom_notification.htm
old-project: kernel
ms.assetid: fa6530a4-13b7-472b-a571-682323edc64e
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PTARGET_DEVICE_CUSTOM_NOTIFICATION, PTARGET_DEVICE_CUSTOM_NOTIFICATION, PTARGET_DEVICE_CUSTOM_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture], TARGET_DEVICE_CUSTOM_NOTIFICATION, TARGET_DEVICE_CUSTOM_NOTIFICATION structure [Kernel-Mode Driver Architecture], _TARGET_DEVICE_CUSTOM_NOTIFICATION, kernel.target_device_custom_notification, kstruct_d_b83ddfbd-9448-4a91-8a64-ab060ba7614f.xml, wdm/PTARGET_DEVICE_CUSTOM_NOTIFICATION, wdm/TARGET_DEVICE_CUSTOM_NOTIFICATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	TARGET_DEVICE_CUSTOM_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: TARGET_DEVICE_CUSTOM_NOTIFICATION, *PTARGET_DEVICE_CUSTOM_NOTIFICATION
req.product: Windows 10 or later.
---

# _TARGET_DEVICE_CUSTOM_NOTIFICATION structure
The <b>TARGET_DEVICE_CUSTOM_NOTIFICATION</b> structure describes a custom device event.

## Syntax
````
typedef struct _TARGET_DEVICE_CUSTOM_NOTIFICATION {
  USHORT       Version;
  USHORT       Size;
  GUID         Event;
  PFILE_OBJECT FileObject;
  LONG         NameBufferOffset;
  UCHAR        CustomDataBuffer[1];
} TARGET_DEVICE_CUSTOM_NOTIFICATION, *PTARGET_DEVICE_CUSTOM_NOTIFICATION;
````

## Members


`CustomDataBuffer`

A variable-length buffer, optionally containing binary data at the start of the buffer, followed by an optional text buffer (word-aligned).

`Event`

Specifies a GUID identifying the event. GUIDs for custom event notification are defined by the components that use this mechanism.

`FileObject`

Pointer to a file object for the device.

`NameBufferOffset`

Specifies the offset, in bytes, from beginning of <b>CustomDataBuffer</b> where text begins. A value of -1 indicates that there is no text.

`Size`

Specifies the size of the structure, in bytes, including the first three standard members plus the event-specific data.

`Version`

Specifies the version of the data structure, currently 1.

## Remarks
Kernel-mode components use this structure for custom event notification:  to signal a custom event (<b>IoReportTargetDeviceChange</b>[<b>Asynchronous</b>]) and when handling a custom event (in a notification callback routine).

This structure accommodates both a variable-length binary data buffer and a variable-length Unicode text buffer. The <i>NameBufferOffset</i> must indicate where the text buffer begins, so the data can be delivered in the appropriate format (ANSI or Unicode) to user-mode applications that registered for handle-based notification with <b>RegisterDeviceNotification</b>. See the Microsoft Windows SDK documentation for information about <b>RegisterDeviceNotification</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\nf-wdm-ioreporttargetdevicechange.md">IoReportTargetDeviceChange</a>



<a href="..\wdm\nf-wdm-ioreporttargetdevicechangeasynchronous.md">IoReportTargetDeviceChangeAsynchronous</a>



<a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TARGET_DEVICE_CUSTOM_NOTIFICATION structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>