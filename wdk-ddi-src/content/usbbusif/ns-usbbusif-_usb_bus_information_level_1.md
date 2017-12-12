---
UID: NS.USBBUSIF._USB_BUS_INFORMATION_LEVEL_1
title: _USB_BUS_INFORMATION_LEVEL_1
author: windows-driver-content
description: The USB_BUS_INFORMATION_LEVEL_1 structure is used in conjunction with the QueryBusInformation interface routine to report information about the bus.
old-location: buses\usb_bus_information_level_1.htm
old-project: usbref
ms.assetid: 518cd3bb-86a8-4960-b140-fabb78fa3519
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USB_BUS_INFORMATION_LEVEL_1, *PUSB_BUS_INFORMATION_LEVEL_1, USB_BUS_INFORMATION_LEVEL_1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_BUS_INFORMATION_LEVEL_1
req.alt-loc: usbbusif.h
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
req.product: Windows 10 or later.
---

# _USB_BUS_INFORMATION_LEVEL_1 structure



## -description
The <b>USB_BUS_INFORMATION_LEVEL_1</b> structure is used in conjunction with the <a href="buses.querybusinformation">QueryBusInformation</a> interface routine to report information about the bus.



## -syntax

````
typedef struct _USB_BUS_INFORMATION_LEVEL_1 {
  ULONG TotalBandwidth;
  ULONG ConsumedBandwidth;
  ULONG ControllerNameLength;
  WCHAR ControllerNameUnicodeString[1];
} USB_BUS_INFORMATION_LEVEL_1, *PUSB_BUS_INFORMATION_LEVEL_1;
````


## -struct-fields

### -field TotalBandwidth

Specifies the total bandwidth, in bits per second, available on the bus. 


### -field ConsumedBandwidth

Specifies the mean bandwidth already in use, in bits per second. 


### -field ControllerNameLength

Specifies the length of symbolic name for the host controller, in Unicode.


### -field ControllerNameUnicodeString

Specifies the symbolic name for the host controller, in Unicode. 


## -remarks
Caller must set the <i>Level</i> parameter of the <a href="buses.querybusinformation">QueryBusInformation</a> routine to 1. 

For more information about how to obtain the proper level of USB interface, see <a href="buses.usb_interfaces">USB Routines</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbbusif.h (include Usbbusif.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.querybusinformation">QueryBusInformation</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_BUS_INFORMATION_LEVEL_1 structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

