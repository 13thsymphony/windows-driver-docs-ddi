---
UID: NS.WDM._TARGET_DEVICE_CUSTOM_NOTIFICATION
title: _TARGET_DEVICE_CUSTOM_NOTIFICATION
author: windows-driver-content
description: The TARGET_DEVICE_CUSTOM_NOTIFICATION structure describes a custom device event.
old-location: kernel\target_device_custom_notification.htm
old-project: kernel
ms.assetid: fa6530a4-13b7-472b-a571-682323edc64e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _TARGET_DEVICE_CUSTOM_NOTIFICATION, TARGET_DEVICE_CUSTOM_NOTIFICATION, *PTARGET_DEVICE_CUSTOM_NOTIFICATION
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
req.alt-api: TARGET_DEVICE_CUSTOM_NOTIFICATION
req.alt-loc: wdm.h
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
req.product: Windows 10 or later.
---

# _TARGET_DEVICE_CUSTOM_NOTIFICATION structure



## -description
The <b>TARGET_DEVICE_CUSTOM_NOTIFICATION</b> structure describes a custom device event. 


## -syntax

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


## -struct-fields

### -field Version

Specifies the version of the data structure, currently 1. 

### -field Size

Specifies the size of the structure, in bytes, including the first three standard members plus the event-specific data. 

### -field Event

Specifies a GUID identifying the event. GUIDs for custom event notification are defined by the components that use this mechanism. 

### -field FileObject

Pointer to a file object for the device.

### -field NameBufferOffset

Specifies the offset, in bytes, from beginning of <b>CustomDataBuffer</b> where text begins. A value of -1 indicates that there is no text.

### -field CustomDataBuffer

A variable-length buffer, optionally containing binary data at the start of the buffer, followed by an optional text buffer (word-aligned). 

## -remarks
Kernel-mode components use this structure for custom event notification:  to signal a custom event (<b>IoReportTargetDeviceChange</b>[<b>Asynchronous</b>]) and when handling a custom event (in a notification callback routine).

This structure accommodates both a variable-length binary data buffer and a variable-length Unicode text buffer. The <i>NameBufferOffset</i> must indicate where the text buffer begins, so the data can be delivered in the appropriate format (ANSI or Unicode) to user-mode applications that registered for handle-based notification with <b>RegisterDeviceNotification</b>. See the Microsoft Windows SDK documentation for information about <b>RegisterDeviceNotification</b>. 

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a>
</dt>
<dt>
<a href="kernel.ioreporttargetdevicechange">IoReportTargetDeviceChange</a>
</dt>
<dt>
<a href="kernel.ioreporttargetdevicechangeasynchronous">IoReportTargetDeviceChangeAsynchronous</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TARGET_DEVICE_CUSTOM_NOTIFICATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
