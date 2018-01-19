---
UID : NI:scsiscan.IOCTL_SCSISCAN_CMD
title : IOCTL_SCSISCAN_CMD
author : windows-driver-content
description : Creates a customized SCSI control descriptor block (CDB) and sends it to the kernel-mode still image driver for SCSI buses.
old-location : image\ioctl_scsiscan_cmd.htm
old-project : image
ms.assetid : af1f4107-f537-4b94-b9b4-c97429878fef
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : _ZONE_DESCRIPTIOR, ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : scsiscan.h
req.include-header : Scsiscan.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_SCSISCAN_CMD
req.alt-loc : Scsiscan.h
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
req.typenames : ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
req.product : Windows 10 or later.
---

# IOCTL_SCSISCAN_CMD IOCTL
Creates a customized SCSI control descriptor block (CDB) and sends it to the kernel-mode still image driver for SCSI buses.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Pointer to a <b>SCSISCAN_CMD</b> structure.

### Input Buffer Length
Size of the input buffer.

### Output Buffer
Pointer to a data buffer. Depending on the type of I/O operation, this buffer might supply or receive data.

### Output Buffer Length
Size of the output buffer.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

    ## Remarks
        When the <b>DeviceloControl</b> function is called with the IOCTL_SCSISCAN_CMD I/O control code, the caller must specify the address of a <a href="..\scsiscan\ns-scsiscan-_scsiscan_cmd.md">SCSISCAN_CMD</a> structure as the function's <i>lpInBuffer</i> parameter. This structure specifies the type of operation being requested. The kernel-mode driver constructs a SCSI Request Block (SRB) from the SCSISCAN_CMD structure's contents.

For SCSI commands that involve data transfers, the <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> function's <i>lpOutBuffer</i> must point to a data buffer. For read operations, this buffer will receive data read from the device. For write operations, the buffer must contain the data to be written.

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.

<b>Code example</b>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | scsiscan.h (include Scsiscan.h) |
| **IRQL** |  |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IOCTL_SCSISCAN_CMD control code%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>