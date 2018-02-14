---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
title: IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
author: windows-driver-content
description: The class driver sends this request to send a zero-length control status handshake on endpoint 0 in the IN direction.
old-location: buses\_ioctl_internal_usbfn_control_status_handshake_in.htm
old-project: usbref
ms.assetid: 5839C1A8-6638-4A42-B7C1-168071C99800
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses._ioctl_internal_usbfn_control_status_handshake_in, IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN control code [Buses], IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN, usbfnioctl/IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbfnioctl.h
req.include-header: 
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
-	usbfnioctl.h
apiname:
-	IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
product: Windows
targetos: Windows
req.typenames: USBFN_USB_STRING, *PUSBFN_USB_STRING
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN IOCTL
The class driver sends this request to send a zero-length control status handshake on endpoint 0 in the IN direction.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A <b>USBFNPIPEID</b> type value that indicates the pipe ID. The pipe ID of the default control endpoint is 0.

### Input Buffer Length
The size of a <b>USBFNPIPEID</b> type.

### Output Buffer
NULL.

### Output Buffer Length
NULL.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.

## Remarks
This request must be sent after sending the <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbfnioctl.h |