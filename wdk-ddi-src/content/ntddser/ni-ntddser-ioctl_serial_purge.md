---
UID : NI:ntddser.IOCTL_SERIAL_PURGE
title : IOCTL_SERIAL_PURGE
author : windows-driver-content
description : The IOCTL_SERIAL_PURGE request cancels the specified requests and deletes data from the specified buffers.
old-location : serports\ioctl_serial_purge.htm
old-project : serports
ms.assetid : 624e6b52-9698-4d74-8923-cf209e72c05c
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : serports.ioctl_serial_purge, IOCTL_SERIAL_PURGE control code [Serial Ports], IOCTL_SERIAL_PURGE, ntddser/IOCTL_SERIAL_PURGE, serref_d52cfcec-8098-4319-b601-14187a77e438.xml
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
req.typenames : SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_PURGE IOCTL
The <b>IOCTL_SERIAL_PURGE</b> request cancels the specified requests and deletes data from the specified buffers. The purge request can be used to cancel all read requests and write requests and to delete all data from the receive buffer and the transmit buffer.

The completion of the purge request does not indicate that the requests canceled by the purge request are completed. A client must verify that the purged requests are completed before the client frees or reuses the corresponding IRPs.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated ULONG that is used to input a <i>purge mask</i>. The client sets the purge mask to a bitwise-OR of one or more of the following purge flags:

### Input Buffer Length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a ULONG.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a ULONG. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that the purge mask is not valid.

## Remarks
Serial.sys and SerCx allow an <b>IOCTL_SERIAL_PURGE</b> request to specify any combination of one or more SERIAL_PURGE_<i>XXX</i> flags. However, SerCx2 is more restrictive.

SerCx2 requires that all read requests be purged if the receive buffer is purged. Thus, if the SERIAL_PURGE_RXCLEAR flag is set in an <b>IOCTL_SERIAL_PURGE</b> request, then either the SerCx2 I/O request queue must not contain any read requests, or the SERIAL_PURGE_RXABORT flag must be set. Otherwise, the <b>IOCTL_SERIAL_PURGE</b> request fails with a STATUS_INVALID_DEVICE_STATE status code.

Similarly, SerCx2 requires that all write requests be purged if the transmit buffer is purged. Thus, if the SERIAL_PURGE_TXCLEAR flag is set in an <b>IOCTL_SERIAL_PURGE</b> request, then either the SerCx2 I/O request queue must must not contain any write requests, or the SERIAL_PURGE_TXABORT flag must be set. Otherwise, the <b>IOCTL_SERIAL_PURGE</b> request fails with a STATUS_INVALID_DEVICE_STATE status code.

For more information about SerCx2, SerCx, and Serial.sys, see <a href="https://msdn.microsoft.com/1EA0221E-0F68-429B-9DA5-4AE2D3394A09">Serial Controller Drivers Overview</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |