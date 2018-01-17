---
UID: NI:ufxbase.IOCTL_INTERNAL_USBFN_DESCRIPTOR_UPDATE
title: IOCTL_INTERNAL_USBFN_DESCRIPTOR_UPDATE
author: windows-driver-content
description: The USB function class extension sends this request to the client driver to update to the endpoint descriptor for the specified endpoint.
old-location: buses\ioctl_internal_usbfn_descriptor_update.htm
old-project: usbref
ms.assetid: 9BA9BC9E-C04C-48F8-B76A-2D6F779BBE05
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USBFN_ACTION, *PUSBFN_ACTION, USBFN_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ufxbase.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_INTERNAL_USBFN_DESCRIPTOR_UPDATE
req.alt-loc: ufxbase.h
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
req.typenames: *PUSBFN_ACTION, USBFN_ACTION
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_DESCRIPTOR_UPDATE IOCTL



## -description
The USB function class extension sends this request to the client driver to update to the endpoint descriptor for the specified endpoint.



## -ioctlparameters

### -input-buffer
The input buffer points to a <b>USBFNPIPEID</b> that specifies the pipe ID for the endpoint.


### -input-buffer-length
The size of a <b>USBFNPIPEID</b> value.


### -output-buffer
The output buffer points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a> structure that describes the endpoint descriptor. To retrieve the structure, the client driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputbuffer.md">WdfRequestRetrieveOutputBuffer</a>.


### -output-buffer-length
The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block

		  The client driver shall complete the request with <b>STATUS_SUCCESS</b> if the request is successful. 
		  Otherwise, the client driver shall complete the driver with to the appropriate error condition, 
		  such as <b>STATUS_INVALID_PARAMETER</b> or <b>STATUS_INSUFFICIENT_RESOURCES</b>.


## -remarks
UFX sends this IOCTL to the command queue created for the endpoint by <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.  The client driver is expected to update the configuration of the endpoint on the controller with the parameters contained in the endpoint descriptor.</p>