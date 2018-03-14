---
UID: NS:usb._URB_GET_CURRENT_FRAME_NUMBER
title: "_URB_GET_CURRENT_FRAME_NUMBER"
author: windows-driver-content
description: The _URB_GET_CURRENT_FRAME_NUMBER structure is used by USB client drivers to retrieve the current frame number.
old-location: buses\_urb_get_current_frame_number.htm
old-project: usbref
ms.assetid: 4c6e5064-83b4-4d3c-ab08-041070128f3c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "_URB_GET_CURRENT_FRAME_NUMBER, _URB_GET_CURRENT_FRAME_NUMBER structure [Buses], buses._urb_get_current_frame_number, usb/_URB_GET_CURRENT_FRAME_NUMBER, usbstrct_b767de1b-63fd-4ac4-b696-78e4d0d83661.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usb.h
api_name:
-	_URB_GET_CURRENT_FRAME_NUMBER
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# _URB_GET_CURRENT_FRAME_NUMBER structure
The <b>_URB_GET_CURRENT_FRAME_NUMBER</b> structure is used by USB client drivers to retrieve the current frame number.

## Syntax
````
struct _URB_GET_CURRENT_FRAME_NUMBER {
  struct URB_HEADER  Hdr;
  ULONG             FrameNumber;
};
````

## Members


`FrameNumber`

Contains the current 32-bit frame number, on the USB bus, on return from the host controller driver.

`Hdr`

Pointer to a <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_GET_CURRENT_FRAME_NUMBER, and <b>Hdr.Length</b> must be <code>sizeof(_URB_GET_CURRENT_FRAME_NUMBER)</code>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usb.h (include Usb.h) |

## See Also

<a href="..\usb\ns-usb-_urb.md">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20_URB_GET_CURRENT_FRAME_NUMBER structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>