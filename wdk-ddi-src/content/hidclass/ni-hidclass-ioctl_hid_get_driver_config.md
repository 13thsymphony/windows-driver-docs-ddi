---
UID : NI:hidclass.IOCTL_HID_GET_DRIVER_CONFIG
title : IOCTL_HID_GET_DRIVER_CONFIG
author : windows-driver-content
description : The IOCTL_HID_GET_DRIVER_CONFIG request retrieves the driver configuration.
old-location : hid\ioctl_hid_get_driver_config.htm
old-project : hid
ms.assetid : F648EF1E-2673-499D-81BF-03B7B2148FA2
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : hid.ioctl_hid_get_driver_config, IOCTL_HID_GET_DRIVER_CONFIG control code [Human Input Devices], IOCTL_HID_GET_DRIVER_CONFIG, hidclass/IOCTL_HID_GET_DRIVER_CONFIG
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
req.typenames : HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
---

# IOCTL_HID_GET_DRIVER_CONFIG IOCTL
The <b>IOCTL_HID_GET_DRIVER_CONFIG</b> 
   request retrieves the driver configuration.

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
| **Header** | hidclass.h (include Hidclass.h) |