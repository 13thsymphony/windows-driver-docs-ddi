---
UID: NI.usbfnioctl.IOCTL_INTERNAL_USBFN_SET_PIPE_STATE
title: IOCTL_INTERNAL_USBFN_SET_PIPE_STATE
author: windows-driver-content
description: The class driver sends this request to set the stall state of the specified USB pipe.
old-location: buses\ioctl_internal_usbfn_set_pipe_state.htm
old-project: usbref
ms.assetid: EB44DE6F-6B88-4F6D-B9AC-3FF7A519C047
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USBFN_USB_STRING, *PUSBFN_USB_STRING, USBFN_USB_STRING
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
req.alt-api: IOCTL_INTERNAL_USBFN_SET_PIPE_STATE
req.alt-loc: usbfnioctl.h
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
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_SET_PIPE_STATE IOCTL



## -description
The class driver sends this request to set the stall state of the specified USB pipe. 



## -ioctlparameters

### -input-buffer
A pointer to a <b>USBFNPIPEID</b> type that specifies the pipe ID.


### -input-buffer-length
The size of a <b>USBFNPIPEID</b> type.


### -output-buffer
A pointer to <b>BOOLEAN</b> value that  specifies the stall state to set. If TRUE,  USB Function Class Extension (UFX) sets the  pipe to stall state; FALSE sets to clear state.



### -output-buffer-length
The size of a <b>BOOLEAN</b>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
UFX completes the request with <b>STATUS_SUCCESS</b>.


## -remarks
This request must be sent after sending the <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="buses.ufxendpointcreate">UfxEndpointCreate</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbfnioctl.h</dt>
</dl>
</td>
</tr>
</table>