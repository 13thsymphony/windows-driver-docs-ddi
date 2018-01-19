---
UID : NI:ntddpar.IOCTL_PAR_SET_READ_ADDRESS
title : IOCTL_PAR_SET_READ_ADDRESS
author : windows-driver-content
description : The IOCTL_PAR_SET_READ_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) read address (channel) for a parallel device.
old-location : parports\ioctl_par_set_read_address.htm
old-project : parports
ms.assetid : d6ea5ac7-d324-4986-bbfb-4decd278acf7
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _OFFLOAD_SECURITY_ASSOCIATION, OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddpar.h
req.include-header : Ntddpar.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_PAR_SET_READ_ADDRESS
req.alt-loc : ntddpar.h
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
req.typenames : OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
---

# IOCTL_PAR_SET_READ_ADDRESS IOCTL
The IOCTL_PAR_SET_READ_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) read address (channel) for a parallel device.



The IOCTL_PAR_SET_READ_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) read address (channel) for a parallel device.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a UCHAR buffer that the client allocates to input a read address. The request sets the buffer to an ECP or EPP read address.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a UCHAR.

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

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to the following value:



<b>Parameters.DeviceIoControl.InputBufferLength</b> is less than the size, in bytes, of a UCHAR.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddpar.h (include Ntddpar.h) |
| **IRQL** |  |

    ## See Also

        <dl>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_par_set_write_address.md">IOCTL_PAR_SET_WRITE_ADDRESS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_PAR_SET_READ_ADDRESS control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>