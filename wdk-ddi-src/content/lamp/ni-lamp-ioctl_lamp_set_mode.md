---
UID : NI:lamp.IOCTL_LAMP_SET_MODE
title : IOCTL_LAMP_SET_MODE
author : windows-driver-content
description : The IOCTL_LAMP_SET_MODE control code sets the mode in which the lamp operates.
old-location : stream\ioctl_lamp_set_mode.htm
old-project : stream
ms.assetid : 188F8AC8-BB1A-43C1-9933-5E03F954C2C0
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : LAMP_MODE, LAMP_MODE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : lamp.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_LAMP_SET_MODE
req.alt-loc : lamp.h
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
req.typenames : LAMP_MODE
---

# IOCTL_LAMP_SET_MODE IOCTL
The <b>IOCTL_LAMP_SET_MODE</b> 
   control code sets the mode in which the lamp operates.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> points to a buffer of type <a href="..\lamp\ne-lamp-lamp_mode.md">LAMP_MODE</a>.

### Input Buffer Length
Length of a <a href="..\lamp\ne-lamp-lamp_mode.md">LAMP_MODE</a>.

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
The driver sets <code>Irp-&gt;IoStatus.Status</code> to <b>STATUS_SUCCESS</b> or the appropriate error status.

If the device has been acquired by a camera driver, the lamp driver should return a <b>STATUS_RESOURCE_IN_USE</b> error via <code>Irp-&gt;IoStatus.Status</code>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | lamp.h |
| **IRQL** |  |