---
UID : NI:usbfnioctl.IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT
title : IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT
author : windows-driver-content
description : The class driver sends this request to initiate an IN transfer to the specified pipe and appends a zero-length packet to indicate the end of the transfer.
old-location : buses\ioctl_internal_usbfn_transfer_in_append_zero_pkt.htm
old-project : usbref
ms.assetid : 3912A632-E9D0-42D5-B7B7-766A92EE8C95
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _USBFN_USB_STRING, *PUSBFN_USB_STRING, USBFN_USB_STRING
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : usbfnioctl.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT
req.alt-loc : usbfnioctl.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PUSBFN_USB_STRING, USBFN_USB_STRING"
req.product : Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT IOCTL
The class driver sends this request to initiate an IN transfer to the specified pipe and appends a zero-length packet to indicate the end of the transfer.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A pointer to a <b>USBFNPIPEID</b> type that specifies the pipe ID.

### Input Buffer Length
The size of a <b>USBFNPIPEID</b> type.

### Output Buffer
The  output buffer points to a data buffer containing the data to be sent. The IN direction is from the host perspective representing an outbound transfer from the device to the host.

### Output Buffer Length
The size of the data to be sent.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.

    ## Remarks
        This request must be sent after sending the <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.

The function controller initiates a transfer in the IN direction on the endpoint and automatically appends a zero-length packet transfer after the data provided in the data buffer is successfully sent. A zero-length packet is only appended by the controller if the size of the transfer payload is a multiple of the endpoint’s maximum packet size.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | usbfnioctl.h |
| **IRQL** |  |