---
UID: NS:usbioctl._USB_ID_STRING
title: "_USB_ID_STRING"
author: windows-driver-content
description: The USB_ID_STRING structure is used to store a string or multi-string.
old-location: buses\usb_id_string.htm
old-project: usbref
ms.assetid: e7af07ed-f1a7-4f66-8824-2e12492d037a
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: PUSB_ID_STRING structure pointer [Buses], USB_ID_STRING, PUSB_ID_STRING, usbioctl/PUSB_ID_STRING, buses.usb_id_string, usbioctl/USB_ID_STRING, USB_ID_STRING structure [Buses], *PUSB_ID_STRING, _USB_ID_STRING
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbioctl.h
apiname:
-	USB_ID_STRING
product: Windows
targetos: Windows
req.typenames: "*PUSB_ID_STRING, USB_ID_STRING"
req.product: Windows 10 or later.
---

# _USB_ID_STRING structure
The <b>USB_ID_STRING</b> structure is used to store a string or multi-string.

## Syntax
````
typedef struct _USB_ID_STRING {
  USHORT  LanguageId;
  ULONG   LengthInBytes;
  PWCHAR  Buffer;
} USB_ID_STRING, *PUSB_ID_STRING;
````

## Members


`Buffer`

Pointer to a string or multi-string.

`LanguageId`

Indicates that language ID of the string.

`LengthInBytes`

Indicates the length (in bytes) of the string pointed to by <b>Buffer</b>, including the terminating <b>NULL</b>.

`Pad`



## Remarks
The reserved members of this structure must be treated as opaque and are reserved for system use.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating systems. Available in Windows Vista and later operating systems. |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_ID_STRING structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>