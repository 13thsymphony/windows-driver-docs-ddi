---
UID: NS:usb._URB_CONTROL_GET_STATUS_REQUEST
title: "_URB_CONTROL_GET_STATUS_REQUEST"
author: windows-driver-content
description: The _URB_CONTROL_GET_STATUS_REQUEST structure is used by USB client drivers to retrieve status from a device, interface, endpoint, or other device-defined target.
old-location: buses\_urb_control_get_status_request.htm
old-project: usbref
ms.assetid: 6a005ff3-951f-462d-84e6-e1fd931c5afc
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "_URB_CONTROL_GET_STATUS_REQUEST, _URB_CONTROL_GET_STATUS_REQUEST structure [Buses], buses._urb_control_get_status_request, usb/_URB_CONTROL_GET_STATUS_REQUEST, usbstrct_b91864c5-b19a-492d-a5dc-1fabdf4c37f9.xml"
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
-	_URB_CONTROL_GET_STATUS_REQUEST
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# _URB_CONTROL_GET_STATUS_REQUEST structure
The _URB_CONTROL_GET_STATUS_REQUEST structure is used by USB client drivers to retrieve status from a device, interface, endpoint, or other device-defined target.

## Syntax
````
struct _URB_CONTROL_GET_STATUS_REQUEST {
  struct URB_HEADER  Hdr;
  PVOID               Reserved;
  ULONG               Reserved0;
  ULONG               TransferBufferLength;
  PVOID               TransferBuffer;
  PMDL                TransferBufferMDL;
  struct URB  *UrbLink;
  struct URB_HCD_AREA  hca;
  UCHAR               Reserved1[4];
  USHORT              Index;
  USHORT              Reserved2;
};
````

## Members


`Hdr`

Pointer to a <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Length</b> must be <code>sizeof(_URB_CONTROL_GET_STATUS_REQUEST)</code>, and <b>Hdr.Function</b> must be one of the following values:

`Reserved`

Reserved. Do not use.

`Reserved0`

Reserved. Do not use.

`TransferBufferLength`

Must be 2. This member specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes sent to or read from the pipe in this member.

`TransferBuffer`

Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>. The bus driver returns a single byte specifying the status for the target.

`TransferBufferMDL`

Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. The bus driver returns a single byte specifying the status for the target. This MDL must be allocated from nonpaged pool.

`UrbLink`

Reserved. Do not use.

`hca`

Reserved. Do not use.

`Reserved1`

Reserved. Do not use.

`Index`

Specifies the device-defined index, returned by a successful configuration request, if the request is for an endpoint or interface. Otherwise, <b>Index</b> must be zero.

`Reserved2`

Reserved. Do not use.

## Remarks
Drivers can use the <a href="..\usbdlib\nf-usbdlib-usbbuildgetstatusrequest.md">UsbBuildGetStatusRequest</a> service routine to format this URB.

The reserved members of this structure must be treated as opaque and are reserved for system use.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usb.h (include Usb.h) |

## See Also

<a href="..\usb\ns-usb-_urb.md">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>