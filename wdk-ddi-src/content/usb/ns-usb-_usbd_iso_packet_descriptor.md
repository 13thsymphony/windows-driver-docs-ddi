---
UID: NS:usb._USBD_ISO_PACKET_DESCRIPTOR
title: "_USBD_ISO_PACKET_DESCRIPTOR"
author: windows-driver-content
description: The USBD_ISO_PACKET_DESCRIPTOR structure is used by USB client drivers to describe an isochronous transfer packet.
old-location: buses\usbd_iso_packet_descriptor.htm
old-project: usbref
ms.assetid: 45ceff8e-a013-45de-be2e-42c6ca30147e
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: usb/PUSBD_ISO_PACKET_DESCRIPTOR, PUSBD_ISO_PACKET_DESCRIPTOR, usb/USBD_ISO_PACKET_DESCRIPTOR, usbstrct_142becb1-b374-467e-9a11-2cda26e69ff4.xml, _USBD_ISO_PACKET_DESCRIPTOR, PUSBD_ISO_PACKET_DESCRIPTOR structure pointer [Buses], USBD_ISO_PACKET_DESCRIPTOR, buses.usbd_iso_packet_descriptor, *PUSBD_ISO_PACKET_DESCRIPTOR, USBD_ISO_PACKET_DESCRIPTOR structure [Buses]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usb.h
apiname:
-	USBD_ISO_PACKET_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PUSBD_ISO_PACKET_DESCRIPTOR, USBD_ISO_PACKET_DESCRIPTOR"
req.product: Windows 10 or later.
---

# _USBD_ISO_PACKET_DESCRIPTOR structure
The <b>USBD_ISO_PACKET_DESCRIPTOR</b>   structure is used by USB client drivers to describe an isochronous transfer packet.

## Syntax
````
typedef struct _USBD_ISO_PACKET_DESCRIPTOR {
  ULONG       Offset;
  ULONG       Length;
  USBD_STATUS Status;
} USBD_ISO_PACKET_DESCRIPTOR, *PUSBD_ISO_PACKET_DESCRIPTOR;
````

## Members


`Length`

Set by the host controller to indicate the actual number of bytes received from the device for isochronous IN transfers. <b>Length</b> not used for isochronous OUT transfers.

`Offset`

Specifies the offset, in bytes, of the buffer for this packet from the beginning of the entire isochronous transfer buffer.

`Status`

Contains the status, on return from the host controller driver, of this transfer packet.

## Remarks
This structure is used as part of an isochronous transfer request to the host controller driver using the <a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a> structure. The <b>Offset</b> member contains the offset from the beginning of the <b>TransferBuffer</b> or <b>TransferBufferMDL</b> members of  <b>_URB_ISOCH_TRANSFER</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usb.h (include Usb.h) |

## See Also

<a href="..\usbdlib\nf-usbdlib-usbd_isochurballocate.md">USBD_IsochUrbAllocate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406225">How to Transfer Data to USB Isochronous Endpoints</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_ISO_PACKET_DESCRIPTOR structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>