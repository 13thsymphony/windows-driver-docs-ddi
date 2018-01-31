---
UID : NI:usbfnioctl.IOCTL_INTERNAL_USBFN_SET_PIPE_STATE
title : IOCTL_INTERNAL_USBFN_SET_PIPE_STATE
author : windows-driver-content
description : The class driver sends this request to set the stall state of the specified USB pipe.
old-location : buses\ioctl_internal_usbfn_set_pipe_state.htm
old-project : usbref
ms.assetid : EB44DE6F-6B88-4F6D-B9AC-3FF7A519C047
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : buses.ioctl_internal_usbfn_set_pipe_state, IOCTL_INTERNAL_USBFN_SET_PIPE_STATE control code [Buses], IOCTL_INTERNAL_USBFN_SET_PIPE_STATE, usbfnioctl/IOCTL_INTERNAL_USBFN_SET_PIPE_STATE
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : USBFN_USB_STRING, *PUSBFN_USB_STRING
req.product : Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_SET_PIPE_STATE IOCTL
The class driver sends this request to set the stall state of the specified USB pipe.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A pointer to a <b>USBFNPIPEID</b> type that specifies the pipe ID.

### Input Buffer Length
The size of a <b>USBFNPIPEID</b> type.

### Output Buffer
A pointer to <b>BOOLEAN</b> value that  specifies the stall state to set. If TRUE,  USB Function Class Extension (UFX) sets the  pipe to stall state; FALSE sets to clear state.

### Output Buffer Length
The size of a <b>BOOLEAN</b>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
UFX completes the request with <b>STATUS_SUCCESS</b>.

## Remarks
This request must be sent after sending the <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | usbfnioctl.h |
| **IRQL** |  |