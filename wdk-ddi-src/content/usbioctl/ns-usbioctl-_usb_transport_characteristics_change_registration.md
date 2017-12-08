---
UID: NS.USBIOCTL._USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
title: _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
author: windows-driver-content
description: Contains registration information for the IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE request.
old-location: buses\usb_transport_characteristics_change_registration.htm
old-project: usbref
ms.assetid: AC05B79E-D293-4EC7-8BF2-D14E3163FB43
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
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
req.alt-api: USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
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

# _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure



## -description
Contains registration information for the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change.md">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> 

request.


## -syntax

````
typedef struct _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION {
  ChangeNotificationInputFlags    ULONG;
  USB_CHANGE_REGISTRATION_HANDLE  Handle;
   USB_TRANSPORT_CHARACTERISTICS  UsbTransportCharacteristics;
} USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION;
````


## -struct-fields

### -field  ULONG

A bitmask set by the client driver to register for change notifications that it is interested in. The following bits are valid:
If 

USB_REGISTER_FOR_TRANSPORT_LATENCY_CHANGE 

is set, the client is notified of changes in transport latency.  


If USB_REGISTER_FOR_TRANSPORT_BANDWIDTH_CHANGE 

is set, the client is notified of changes in bandwidth. 


### -field  Handle

An opaque handle for this registration.

### -field  UsbTransportCharacteristics

A <a href="buses.usb_transport_characteristics">USB_TRANSPORT_CHARACTERISTICS</a> structure that is filled by the USB driver stack with the initial values of the transport characteristics. 


## -remarks
The registration handle received in this request is valid until the caller sends the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_unregister_for_transport_characteristics_change.md">IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> request to unregister for notifications.

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
<a href="..\usbioctl\ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change.md">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
