---
UID : NI:ntddser.IOCTL_SERIAL_IMMEDIATE_CHAR
title : IOCTL_SERIAL_IMMEDIATE_CHAR
author : windows-driver-content
description : The IOCTL_SERIAL_IMMEDIATE_CHAR request causes a specified character to be transmitted as soon as possible.
old-location : serports\ioctl_serial_immediate_char.htm
old-project : serports
ms.assetid : 1bbae06c-1279-41da-82d8-ccbfe13cde9a
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
req.alt-api : IOCTL_SERIAL_IMMEDIATE_CHAR
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

# IOCTL_SERIAL_IMMEDIATE_CHAR IOCTL
The <b>IOCTL_SERIAL_IMMEDIATE_CHAR</b> request causes a specified character to be transmitted as soon as possible. The immediate character request completes immediately after any other write that might be in progress. Only one immediate character request can be pending at a time.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to the UCHAR value to transmit immediately.

### Input Buffer Length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a UCHAR.

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
If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a UCHAR. Otherwise, <b>Information</b> is set to zero.

The <b>Status</b> member is set to one of the <a href="serial_device_control_requests.htm#generic_status_values_for_serial_device_control_requests">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that a previous immediate character request is pending.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddser.h (include Ntddser.h) |
| **IRQL** |  |