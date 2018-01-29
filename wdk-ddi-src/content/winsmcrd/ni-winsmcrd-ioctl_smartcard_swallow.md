---
UID : NI:winsmcrd.IOCTL_SMARTCARD_SWALLOW
title : IOCTL_SMARTCARD_SWALLOW
author : windows-driver-content
description : The IOCTL_SMARTCARD_SWALLOW request causes the smart card reader to swallow the card.
old-location : smartcrd\ioctl_smartcard_swallow.htm
old-project : smartcrd
ms.assetid : c229769d-8798-436e-bd26-9dfd507fba9c
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : smartcrd.ioctl_smartcard_swallow, IOCTL_SMARTCARD_SWALLOW control code [Smart Card Reader Devices], IOCTL_SMARTCARD_SWALLOW, winsmcrd/IOCTL_SMARTCARD_SWALLOW, scioctls_71a14048-5e68-45c7-ad72-03c6350b9072.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : winsmcrd.h
req.include-header : Winsmcrd.h
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
req.typenames : "*PDOT11_WPS_DEVICE_NAME, DOT11_WPS_DEVICE_NAME"
req.product : Windows 10 or later.
---

# IOCTL_SMARTCARD_SWALLOW IOCTL
The IOCTL_SMARTCARD_SWALLOW request causes the smart card reader to swallow the card.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None

### Input Buffer Length
<text></text>

### Output Buffer
None

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The smart card was swallowed.

</td>
</tr>
<tr>
<td>
STATUS_NO_MEDIA

</td>
<td>
No smart card is in the reader.

</td>
</tr>
<tr>
<td>
STATUS_IO_TIMEOUT

</td>
<td>
The operation timed out.

</td>
</tr>
<tr>
<td>
STATUS_NOT_SUPPORTED

</td>
<td>
The reader does not support swallowing.

</td>
</tr>
</table>

## Remarks
The <b>Information</b> member must be set to zero.

The <b>Status</b> member is set to one of the values in the status block table.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | winsmcrd.h (include Winsmcrd.h) |
| **IRQL** |  |