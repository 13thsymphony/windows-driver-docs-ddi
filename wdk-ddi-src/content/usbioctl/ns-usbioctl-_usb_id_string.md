---
UID: NS.USBIOCTL._USB_ID_STRING
title: _USB_ID_STRING
author: windows-driver-content
description: The USB_ID_STRING structure is used to store a string or multi-string.
old-location: buses\usb_id_string.htm
old-project: UsbRef
ms.assetid: e7af07ed-f1a7-4f66-8824-2e12492d037a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _USB_ID_STRING, USB_ID_STRING, PUSB_ID_STRING, *PUSB_ID_STRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_ID_STRING
req.alt-loc: usbioctl.h
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

# _USB_ID_STRING structure



## -description
The <b>USB_ID_STRING</b> structure is used to store a string or multi-string.



## -syntax

````
typedef struct _USB_ID_STRING {
  USHORT  LanguageId;
  ULONG   LengthInBytes;
  PWCHAR  Buffer;
} USB_ID_STRING, *PUSB_ID_STRING;
````


## -struct-fields

### -field LanguageId

Indicates that language ID of the string.


### -field LengthInBytes

Indicates the length (in bytes) of the string pointed to by <b>Buffer</b>, including the terminating <b>NULL</b>. 


### -field Buffer

Pointer to a string or multi-string.


## -remarks
The reserved members of this structure must be treated as opaque and are reserved for system use.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later operating systems. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbioctl.h (include Usbioctl.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USB_ID_STRING structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

