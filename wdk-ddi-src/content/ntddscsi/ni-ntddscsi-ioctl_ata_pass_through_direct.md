---
UID: NI:ntddscsi.IOCTL_ATA_PASS_THROUGH_DIRECT
title: IOCTL_ATA_PASS_THROUGH_DIRECT
author: windows-driver-content
description: Allows an application to send almost any ATA command to a target device, with the following restrictions:\_If a class driver for the target type of device exists, the application must send the request to the class driver.
old-location: storage\ioctl_ata_pass_through_direct.htm
old-project: storage
ms.assetid: 705918c7-c4ea-4495-b87f-2904f7d45ac0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_ATA_PASS_THROUGH_DIRECT, IOCTL_ATA_PASS_THROUGH_DIRECT control code [Storage Devices], k307_8f1da276-e1bf-405e-8e01-a633b8671d5f.xml, ntddscsi/IOCTL_ATA_PASS_THROUGH_DIRECT, storage.ioctl_ata_pass_through_direct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Server 2003.
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
-	IOCTL_ATA_PASS_THROUGH_DIRECT
product: Windows
targetos: Windows
req.typenames: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_ATA_PASS_THROUGH_DIRECT IOCTL
Allows an application to send almost any ATA command to a target device, with the following restrictions: 

<ul>
<li>
If a class driver for the target type of device exists, the application must send the request to the class driver. Thus, an application can send this request directly to the system port driver for a target logical unit only if there is no class driver for the device. 

</li>
<li>
The application <i>must</i> use this request rather than <a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through.md">IOCTL_ATA_PASS_THROUGH</a> if the embedded ATA command might require the underlying miniport driver to access memory directly. 

</li>
</ul>
If the ATA command requests a data transfer operation, the caller must set up a cache-aligned buffer from which, or into which, the driver can transfer data directly. The IOCTL_ATA_PASS_THROUGH_DIRECT request is typically used for transferring large amounts of data (more than 16 KB).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size in bytes of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The value of <b>InputBufferLength</b> is fixed and does not depend on the amount of data transferred. It is equal to <b>sizeof</b>(ATA_PASS_THROUGH_DIRECT). If the size of the buffer is less than <b>sizeof</b>(ATA_PASS_THROUGH_DIRECT), the port driver fails the I/O request and returns an error. 

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an <a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_direct.md">ATA_PASS_THROUGH_DIRECT</a> structure that includes a set of task file input registers that indicate the sort of command to be performed. The caller must initialize all the members of this structure except for <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b>, which the port driver fills in. For a data-out command, the <b>DataBuffer</b> member of <b>ATA_PASS_THROUGH_DIRECT</b> must point to a cache-aligned buffer containing the data to be written.

### Input Buffer Length
<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size in bytes of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The value of <b>InputBufferLength</b> is fixed and does not depend on the amount of data transferred. It is equal to <b>sizeof</b>(ATA_PASS_THROUGH_DIRECT). If the size of the buffer is less than <b>sizeof</b>(ATA_PASS_THROUGH_DIRECT), the port driver fails the I/O request and returns an error.

### Output Buffer
The port driver formats the return data using an <a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_direct.md">ATA_PASS_THROUGH_DIRECT</a> structure that it stores in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 

The port driver stores the transferred data in the cache-aligned buffer pointed to by the <b>DataBuffer</b> member of <a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_direct.md">ATA_PASS_THROUGH_DIRECT</a>.

The port driver fills the <b>CurrentTaskFile</b> member of <a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_direct.md">ATA_PASS_THROUGH_DIRECT</a> with the values present in the device's output registers at the completion of the ATA command. The application is responsible for interpreting the contents of the output registers to determine what errors, if any, were returned by the device.

### Output Buffer Length
The port driver updates the <b>DataTransferLength</b> member of the <a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_direct.md">ATA_PASS_THROUGH_DIRECT</a> structure to indicate the amount of data that was transferred from the device.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> member is set to the number of bytes returned in the output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The <b>Status</b> member is set to STATUS_SUCCESS or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INVALID_PARAMETER if the input <b>Length</b> value in <a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_direct.md">ATA_PASS_THROUGH_DIRECT</a> is improperly set.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Server 2003. Available starting with Windows Server 2003. |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through.md">IOCTL_ATA_PASS_THROUGH</a>



<a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_direct.md">ATA_PASS_THROUGH_DIRECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_ATA_PASS_THROUGH_DIRECT control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>