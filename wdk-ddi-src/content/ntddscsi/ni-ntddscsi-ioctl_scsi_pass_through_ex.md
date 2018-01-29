---
UID : NI:ntddscsi.IOCTL_SCSI_PASS_THROUGH_EX
title : IOCTL_SCSI_PASS_THROUGH_EX
author : windows-driver-content
description : The IOCTL_SCSI_PASS_THROUGH_EX control code request is the extended version of the IOCTL_SCSI_PASS_THROUGH request. This request provides support for bidirectional data transfers and allows a command data block (CDB) &gt; 16 bytes.
old-location : storage\ioctl_scsi_pass_through_ex.htm
old-project : storage
ms.assetid : BDF4375D-660D-4AF0-A692-16EEA59954B3
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_scsi_pass_through_ex, IOCTL_SCSI_PASS_THROUGH_EX control code [Storage Devices], IOCTL_SCSI_PASS_THROUGH_EX, ntddscsi/IOCTL_SCSI_PASS_THROUGH_EX
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddscsi.h
req.include-header : Ntddscsi.h
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
req.typenames : MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_SCSI_PASS_THROUGH_EX IOCTL
The <b>IOCTL_SCSI_PASS_THROUGH_EX</b>
     control code request is the extended version of the <b>IOCTL_SCSI_PASS_THROUGH</b> request. This request provides support for bidirectional data transfers and allows a command data block (CDB) &gt; 16 bytes.

Allows an application to send almost any SCSI command to a target device, with the following restrictions:
<ul>
<li>
Multitarget commands, such as COPY, are not allowed.

</li>
<li>
If a class driver for the target type of device exists, the request must be sent to that class driver. Thus, an application can send this request directly to the system port driver for a target logical unit (LU) only if there is no class driver for the type of device that is connected to that LU. The system port driver does not check to determine if a device has been claimed by a class driver before it processes a pass-through request. Therefore, if an application bypasses a class driver that has claimed a device and sends a pass-through request for that device directly to the port driver, a conflict for control of the device can occur between the class driver and the application. If a pass-through request is sent to an adapter device object and if it originates from user mode and targets an LU that is claimed by a class driver, Storport fails the request with STATUS_INVALID_DEVICE_REQUEST. If the request is sent to an LU device object, originates in kernel mode, or targets an unclaimed LU, it is passed to the miniport driver.

</li>
<li>
This request cannot be used if the CDB might require the underlying miniport driver to access memory directly. If the caller's CDB might require direct access to memory, use <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a> instead. 

</li>
<li>
Applications must not attempt to send a pass-through request asynchronously. All pass-through requests must be synchronous. 

</li>
<li>
Applications do not require administrative privileges to send a pass-through request to a device, but they must have read/write access to the device. 

</li>
</ul>The calling application creates the SCSI command descriptor block, which can include a request for request-sense data if a CHECK CONDITION occurs. 

<b>IOCTL_SCSI_PASS_THROUGH_EX</b> is a buffered device control request. To bypass buffering in system memory, callers should use <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>. When handling an <b>IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</b> request, the system locks down the buffer in user memory and the device accesses this memory directly. 

This request is typically used for transferring small amounts of data (&lt;16K).

Applications can send this request by means of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> request. 

Storage class drivers set the minor IRP number to IRP_MN_SCSI_CLASS to indicate that the request has been processed by a storage class driver. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
This structure includes a SCSI CDB, which must be initialized by the caller except for the path, target ID, and logical unit number (LUN), which are filled in by the port driver. For a data-out command, the data to be transferred is included in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> at <b>DataInBufferOffset</b> in the <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_ex.md">SCSI_PASS_THROUGH_EX</a> structure. However, the caller must allocate additional storage, immediately following <b>SCSI_PASS_THROUGH_EX</b>, if the caller asks for request-sense data.

### Input Buffer Length
<i>
       Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be at least (<i>sense data size</i> + <b>sizeof</b>(SCSI_PASS_THROUGH_EX)). The size of the <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_ex.md">SCSI_PASS_THROUGH_EX</a> structure varies, depending on the value specified in <b>DataInTransferLength</b> .

### Output Buffer
The port driver returns any request-sense data and any data transferred from the device to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The <b>SenseInfoLength</b> and <b>DataOutTransferLength</b> in the <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_ex.md">SCSI_PASS_THROUGH_EX</a> structure are updated to indicate the amount of data transferred.

### Output Buffer Length
The <b>SenseInfoLength</b> and <b>DataOutTransferLength</b> in the <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_ex.md">SCSI_PASS_THROUGH_EX</a> structure are updated to indicate the amount of data transferred.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes returned in the output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INVALID_PARAMETER if the input <b>Length</b> value in <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_ex.md">SCSI_PASS_THROUGH_EX</a> is improperly set.

## Remarks
In order to issue an <b>IOCTL_SCSI_PASS_THROUGH_EX</b> request, the underlying storage device must support extended SRBs. This means that the supported SRB type is <b>SRB_TYPE_STORAGE_REQUEST_BLOCK</b>. An application can query for SRB support with the <b>IOCTL_STORAGE_QUERY_PROPERTY</b> request with a query type of <b>PropertyStandardQuery</b> and a property type of <b>StorageDeviceProperty</b>. The <b>SrbType</b> member returned in the <a href="..\ntddstor\ns-ntddstor-_storage_adapter_descriptor.md">STORAGE_ADAPTER_DESCRIPTIOR</a> structure will indicate either <b>SRB_TYPE_SCSI_REQUEST_BLOCK</b> or <b>SRB_TYPE_STORAGE_REQUEST_BLOCK</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddscsi.h (include Ntddscsi.h) |
| **IRQL** |  |

## See Also

<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_ex.md">SCSI_PASS_THROUGH_EX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_PASS_THROUGH_EX control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>