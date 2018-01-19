---
UID : NI:ntddser.IOCTL_SERIAL_RESET_DEVICE
title : IOCTL_SERIAL_RESET_DEVICE
author : windows-driver-content
description : The IOCTL_SERIAL_RESET_DEVICE request resets a serial device.
old-location : serports\ioctl_serial_reset_device.htm
old-project : serports
ms.assetid : af7482b4-4622-40b7-af7a-c952813e7095
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SdBusSubmitRequestAsync
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddser.h
req.include-header : Ntddser.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_SERIAL_RESET_DEVICE
req.alt-loc : Ntddser.h
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
req.typenames : SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_RESET_DEVICE IOCTL
The <b>IOCTL_SERIAL_RESET_DEVICE</b> request resets a serial device.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="serial_device_control_requests.htm#generic_status_values_for_serial_device_control_requests">Generic Status Values for Serial Device Control Requests</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddser.h (include Ntddser.h) |
| **IRQL** |  |