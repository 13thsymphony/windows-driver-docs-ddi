---
UID: NS:usbspec._USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
title: "_USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR"
author: windows-driver-content
description: The USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR structure is used by USB client drivers to retrieve a USB-defined SuperSpeed Endpoint Companion descriptor. For more information, see section 9.6.7 and Table 9-20 in the official USB 3.0 specification.
old-location: buses\usb_superspeed_endpoint_companion_descriptor.htm
old-project: usbref
ms.assetid: 725ADCA2-FE86-4131-8D70-2BF63F26F89D
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR structure pointer [Buses], USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR structure [Buses], _USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, buses.usb_superspeed_endpoint_companion_descriptor, usbspec/PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, usbspec/USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbspec.h
req.include-header: Usbspec.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: None supported
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
-	usbspec.h
api_name:
-	USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
req.product: Windows 10 or later.
---

# _USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR structure
The <b>USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR</b> structure is used by USB client drivers to retrieve a USB-defined SuperSpeed Endpoint Companion descriptor.

 For more information, see section 9.6.7 and Table 9-20 in the official USB 3.0 specification.

## Syntax
````
typedef struct _USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR {
  UCHAR  bLength;
  UCHAR  bDescriptorType;
  UCHAR  bMaxBurst;
  union {
    UCHAR  AsUchar;
    struct {
      UCHAR MaxStreams  :5;
      UCHAR Reserved1  :3;
    } Bulk;
    struct {
      UCHAR Mult  :2;
      UCHAR Reserved2  :6;
    } Isochronous;
  } bmAttributes;
  USHORT wBytesPerInterval;
} USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR;
````

## Members


`bLength`

Specifies the length, in bytes, of this descriptor.

`bDescriptorType`

Specifies the descriptor type. Must be set to USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR.

`bMaxBurst`

Specifies the maximum number of packets that the endpoint can send or receive as a part of a burst.

`bmAttributes`

#### AsUchar

Specifies the length of the structures.

`wBytesPerInterval`

Number of bytes per interval.

## Remarks
A client driver that supports streams associated with a bulk endpoint, uses <b>USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR</b> to get the maximum number of streams supported by the endpoint. That information is required by the client driver in an open-streams request. In the request, the specified value for <b>NumberOfStreams</b> member of the <a href="..\usb\ns-usb-_urb_open_static_streams.md">_URB_OPEN_STATIC_STREAMS</a> structure cannot exceed the <b>MaxStreams</b> value reported in <b>USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR</b>. For more information about opening streams, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | usbspec.h (include Usbspec.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>