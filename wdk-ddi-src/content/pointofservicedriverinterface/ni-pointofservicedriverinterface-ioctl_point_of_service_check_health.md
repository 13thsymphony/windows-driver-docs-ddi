---
UID : NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_CHECK_HEALTH
title : IOCTL_POINT_OF_SERVICE_CHECK_HEALTH
author : windows-driver-content
description : This I/O control function checks the device health.
old-location : pos\ioctl_point_of_service_check_health.htm
old-project : pos
ms.assetid : b11be48b-e791-4599-80da-2446791f3816
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _PosPropertyId, PosPropertyId
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
req.alt-api : IOCTL_POINT_OF_SERVICE_CHECK_HEALTH
req.alt-loc : pointofservicedriverinterface.h
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
req.typenames : PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_CHECK_HEALTH IOCTL
This I/O control function checks the device health.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Pointer to the input buffer, a <a href="..\pointofservicecommontypes\ne-pointofservicecommontypes-driverunifiedposhealthchecklevel.md">UnifiedPosHealthCheckLevel</a> variable.

### Input Buffer Length
Size of the input buffer, in bytes. Set to sizeof(<i>UnifiedPosHealthCheckLevel</i>).

### Output Buffer
Pointer to a buffer that receives a <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posstringtype.md">PosStringType</a> followed by the contents of the health string.

### Output Buffer Length
Size of the output buffer, in bytes. Set to sizeof(<i>PosStringType</i>) + enough room to hold the health string.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following is a common error value:



The driver does not provide health strings.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | pointofservicedriverinterface.h (include Pointofservicedriverinterface.h) |
| **IRQL** |  |