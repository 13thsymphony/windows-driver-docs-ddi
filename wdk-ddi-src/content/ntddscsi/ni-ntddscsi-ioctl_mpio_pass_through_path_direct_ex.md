---
UID: NI:ntddscsi.IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX
title: IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX
author: windows-driver-content
description: The IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX control code request is the extended version of the IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT request. This request provides support for bidirectional data transfers and allows a command data block (CDB) &gt; 16 bytes.
old-location: storage\ioctl_mpio_pass_through_path_direct_ex.htm
old-project: storage
ms.assetid: 2B5AF281-C080-4ED9-9C58-5757CDE0117A
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX, IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX control code [Storage Devices], ntddscsi/IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX, storage.ioctl_mpio_pass_through_path_direct_ex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddscsi.h
api_name:
-	IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX
product:
- Windows
targetos: Windows
req.typenames: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX IOCTL
The <b>IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX</b> control code request 
     is the extended version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560495">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a> request. This request provides support for bidirectional data transfers and allows a command data block (CDB) &gt; 16 bytes.

This I/O control code allows an application or kernel driver to send a SCSI command to a designated real LUN. The following restrictions apply to the use of this I/O control code:
<ul>
<li>
If a class driver for the pseudo LUN exists, the application must send the request to that class driver. Thus, an application can send this request directly to an MPIO only if there is no class driver for the device.

</li>
<li>
All pass-through requests must be synchronous.

</li>
<li>
Applications do not require administrative privileges to send a pass-through request to a device, but they must have read/write access to the device.

</li>
<li>
The request comprises a SCSI pass-through request (in an embedded <a href="https://msdn.microsoft.com/library/windows/hardware/ff565346">SCSI_PASS_THROUGH_DIRECT</a> structure) as well as certain directives.

</li>
<li>
The SCSI pass-through structure should meet the requirements for such, as described in <a href="https://msdn.microsoft.com/library/windows/hardware/ff565346">SCSI_PASS_THROUGH_DIRECT</a>.

</li>
<li>
If the request is to be sent through the DSM that claimed the real LUN, that must be indicated. In such a case, the DSM itself must indicate the same real LUN. Otherwise, the request will fail.

</li>
<li>
The request must specify the real LUN that is comprised by the pseudo LUN in terms of the former's SCSI address or its MPIO <b>PathId</b>, but not both.

</li>
</ul>

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Input Buffer Length
The buffer must be at least <b>sizeof</b>(MPIO_PASS_THROUGH_PATH_DIRECT_EX) or, if sent by a 32-bit application in a 64-bit operating system, <b>sizeof</b>(MPIO_PASS_THROUGH_PATH_DIRECT32_EX).

### Output Buffer
The port driver returns any request-sense data and any data that is transferred from the device to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
The <b>SenseInfoLength</b> and <b>DataOutTransferLength</b> in the embedded <a href="https://msdn.microsoft.com/library/windows/hardware/jj553713">SCSI_PASS_THROUGH_DIRECT_EX</a> structure are updated to indicate the amount of data that is transferred.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes returned in the output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INVALID_PARAMETER if the input <b>Length</b> value in the embedded <a href="https://msdn.microsoft.com/library/windows/hardware/jj553713">SCSI_PASS_THROUGH_DIRECT_EX</a> is improperly set.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj602802">MPIO_PASS_THROUGH_PATH_DIRECT_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj553713">SCSI_PASS_THROUGH_DIRECT_EX</a>