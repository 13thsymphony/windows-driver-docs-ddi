---
UID : NS:usbioctl._USB_HUB_NAME
title : "_USB_HUB_NAME"
author : windows-driver-content
description : The USB_HUB_NAME structure stores the hub's symbolic device name.
old-location : buses\usb_hub_name.htm
old-project : usbref
ms.assetid : c213d811-a690-41b4-bed1-ec9890e8be46
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : usbioctl/PUSB_HUB_NAME, USB_HUB_NAME, usbstrct_d20b3e12-7b5c-408d-929e-2d781a765f56.xml, *PUSB_HUB_NAME, PUSB_HUB_NAME structure pointer [Buses], buses.usb_hub_name, usbioctl/USB_HUB_NAME, _USB_HUB_NAME, PUSB_HUB_NAME, USB_HUB_NAME structure [Buses]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usbioctl.h
req.include-header : Usbioctl.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : USB_HUB_NAME, *PUSB_HUB_NAME
req.product : Windows 10 or later.
---

# _USB_HUB_NAME structure
The <b>USB_HUB_NAME</b> structure stores the hub's symbolic device name.

## Syntax
````
typedef struct _USB_HUB_NAME {
  ULONG ActualLength;
  WCHAR HubName[1];
} USB_HUB_NAME, *PUSB_HUB_NAME;
````

## Members


`ActualLength`

The size of the Unicode string pointed to by <b>HubName</b>.  The <b>ActualLength</b> value indicates the length of the string and not the entire structure.

`HubName`

A NULL-terminated Unicode string that contains the hub's symbolic device name.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>

<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_get_controller_name.md">IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_HUB_NAME structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>