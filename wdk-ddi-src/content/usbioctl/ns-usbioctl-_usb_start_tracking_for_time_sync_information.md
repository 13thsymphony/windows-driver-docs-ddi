---
UID: NS.USBIOCTL._USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION
title: _USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION
author: windows-driver-content
description: The input and output buffer for the IOCTL_USB_START_TRACKING_FOR_TIME_SYNC request.
old-location: buses\usb_start_tracking_for_time_sync_information.htm
old-project: UsbRef
ms.assetid: 2C82743C-2675-4196-839D-885EE17B2A7A
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, *PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION
req.alt-loc: Usbioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# _USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION structure



## -description
The input and output buffer for the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_start_tracking_for_time_sync.md">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a> request.



## -syntax

````
typedef struct _USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION {
  HANDLE  TimeTrackingHandle;
  BOOLEAN IsStartupDelayTolerable;
} USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, *PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION;
````


## -struct-fields

### -field TimeTrackingHandle

Registration handle for time sync tracking retrieved through the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_start_tracking_for_time_sync.md">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a> request. On input, this handle must be set to NULL. On output, the USB driver stack sets this member to the assigned handle. 


### -field IsStartupDelayTolerable

On input, the caller must specify whether the initial startup latency of up to 2.048 seconds is tolerable. TRUE indicates that the caller can tolerate the initial startup latency FALSE, the registration is delayed until the USB driver stack is able to detect a valid frame or microframe boundary. 




## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbioctl.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usbioctl\ni-usbioctl-ioctl_usb_start_tracking_for_time_sync.md">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

