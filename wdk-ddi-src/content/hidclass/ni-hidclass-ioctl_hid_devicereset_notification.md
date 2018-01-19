---
UID : NI:hidclass.IOCTL_HID_DEVICERESET_NOTIFICATION
title : IOCTL_HID_DEVICERESET_NOTIFICATION
author : windows-driver-content
description : The IOCTL_HID_DEVICERESET_NOTIFICATION request is sent by the HID client driver to HID class driver to wait for a device-initiated reset event.
old-location : hid\ioctl_hid_devicereset_notification.htm
old-project : hid
ms.assetid : 3A9047BE-C974-45E1-89C7-BF0A5F58DD8B
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
req.alt-api : IOCTL_HID_DEVICERESET_NOTIFICATION
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

# IOCTL_HID_DEVICERESET_NOTIFICATION IOCTL
The <b>IOCTL_HID_DEVICERESET_NOTIFICATION</b> 
   request is sent by the HID client driver to HID class driver to wait for a device-initiated reset event.

Only one device reset notification request is allowed at any one  time.

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
I<b>rp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | hidclass.h (include Hidclass.h) |
| **IRQL** |  |