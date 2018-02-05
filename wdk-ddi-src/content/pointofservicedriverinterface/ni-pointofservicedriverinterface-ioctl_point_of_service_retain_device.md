---
UID : NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE
title : IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE
author : windows-driver-content
description : This I/O control function is used to keep a claim on a device when a client is notified that its claim on the device is being contested by another client.
old-location : pos\ioctl_point_of_service_retain_device.htm
old-project : pos
ms.assetid : c221862f-99db-4815-812f-8b22b46fff4a
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : pos.ioctl_point_of_service_retain_device, IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE control code, IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : pointofservicedriverinterface.h
req.include-header : Pointofservicedriverinterface.h
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
req.typenames : PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE IOCTL
This I/O control function is used to keep a claim on a device when a client is notified that its claim on the device is being contested by another client.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Not used with this operation; set to <b>NULL</b>.

### Input Buffer Length
Not used with this operation; set to <b>0</b> (zero).

### Output Buffer
Not used with this operation; set to <b>NULL</b>.

### Output Buffer Length
Not used with this operation; set to <b>0</b> (zero)

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following list shows common error values:

## Remarks
<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>

This IOCTL only works if the client has previously called <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_claim_device.md">IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE</a>.

When handling this IOCTL, the driver can call <a href="..\poscx\nf-poscx-poscxretaindevice.md">PosCxRetainDevice</a>. The driver writer does not need to handle claim contention because the PosCx library determines who gets the claim.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include Pointofservicedriverinterface.h) |