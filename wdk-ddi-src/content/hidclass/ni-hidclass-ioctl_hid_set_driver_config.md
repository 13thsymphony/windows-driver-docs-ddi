---
UID : NI:hidclass.IOCTL_HID_SET_DRIVER_CONFIG
title : IOCTL_HID_SET_DRIVER_CONFIG
author : windows-driver-content
description : The IOCTL_HID_SET_DRIVER_CONFIG request sets the driver configuration.
old-location : hid\ioctl_hid_set_driver_config.htm
old-project : hid
ms.assetid : E20A1105-CB86-4CE3-91A4-23B08B4D0393
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : _HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : hidclass.h
req.include-header : Hidclass.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_HID_SET_DRIVER_CONFIG
req.alt-loc : hidclass.h
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
req.typenames : "*PHDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT"
---

# IOCTL_HID_SET_DRIVER_CONFIG IOCTL
The <b>IOCTL_HID_SET_DRIVER_CONFIG</b> 
   request sets the driver configuration.

This IOCTL is reserved for system use.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<text></text>

### Input Buffer Length
<text></text>

### Output Buffer
<text></text>

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | hidclass.h (include Hidclass.h) |
| **IRQL** |  |