---
UID : NI:ntddscsi.IOCTL_SCSI_PASS_THROUGH_DIRECT
title : IOCTL_SCSI_PASS_THROUGH_DIRECT
author : windows-driver-content
description : Allows an application to send almost any SCSI command to a target device, with the following restrictions:Multitarget commands, such as COPY, are not allowed.Bidirectional data transfer operations are not supported.If a class driver for the target type of device exists, the request must be sent to that class driver. Thus, an application can send this request directly to the system port driver for a target logical unit only if there is no class driver for the type of device connected to that LU.This request must be made if the input CDB might require the underlying miniport driver to access memory directly.The calling application creates the SCSI command descriptor block, which can include a request for request-sense data if a CHECK CONDITION occurs. If the CDB requests a data transfer operation, the caller must set up an adapter device aligned buffer from which or into which the miniport driver can transfer data directly. This request is typically used for transferring larger amounts of data (&gt;16K).Applications can send this request by means of an IRP_MJ_DEVICE_CONTROL request. Storage class drivers set the minor IRP number to IRP_MN_SCSI_CLASS to indicate that the request has been processed by a storage class driver.
old-location : storage\ioctl_scsi_pass_through_direct.htm
old-project : storage
ms.assetid : 7706e861-b8d6-41c3-9b64-371de4f58d48
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
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
req.alt-api : IOCTL_SCSI_PASS_THROUGH_DIRECT
req.alt-loc : Ntddscsi.h
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
req.typenames : "*PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE"
---

# IOCTL_SCSI_PASS_THROUGH_DIRECT IOCTL
Allows an application to send almost any SCSI command to a target device, with the following restrictions:

<ul>
<li>
Multitarget commands, such as COPY, are not allowed.

</li>
<li>
Bidirectional data transfer operations are not supported.

</li>
<li>
If a class driver for the target type of device exists, the request must be sent to that class driver. Thus, an application can send this request directly to the system port driver for a target logical unit only if there is no class driver for the type of device connected to that LU.

</li>
<li>
This request <i>must</i> be made if the input CDB might require the underlying miniport driver to access memory directly.

</li>
</ul>
The calling application creates the SCSI command descriptor block, which can include a request for request-sense data if a CHECK CONDITION occurs. If the CDB requests a data transfer operation, the caller must set up an adapter device aligned buffer from which or into which the miniport driver can transfer data directly. This request is typically used for transferring larger amounts of data (&gt;16K).

Applications can send this request by means of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> request. 

Storage class drivers set the minor IRP number to IRP_MN_SCSI_CLASS to indicate that the request has been processed by a storage class driver. 



Allows an application to send almost any SCSI command to a target device, with the following restrictions:

Multitarget commands, such as COPY, are not allowed.

Bidirectional data transfer operations are not supported.

If a class driver for the target type of device exists, the request must be sent to that class driver. Thus, an application can send this request directly to the system port driver for a target logical unit only if there is no class driver for the type of device connected to that LU.

This request <i>must</i> be made if the input CDB might require the underlying miniport driver to access memory directly.

The calling application creates the SCSI command descriptor block, which can include a request for request-sense data if a CHECK CONDITION occurs. If the CDB requests a data transfer operation, the caller must set up an adapter device aligned buffer from which or into which the miniport driver can transfer data directly. This request is typically used for transferring larger amounts of data (&gt;16K).

Applications can send this request by means of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> request. 

Storage class drivers set the minor IRP number to IRP_MN_SCSI_CLASS to indicate that the request has been processed by a storage class driver.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
This structure includes a SCSI CDB, which must be initialized by the caller except for the path, target ID, and LUN, which are filled in by the port driver. For a data-out command, the data to be transferred must be in an adapter device aligned buffer. The <b>DataBuffer</b> member of <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct.md">SCSI_PASS_THROUGH_DIRECT</a> is a pointer to this adapter device aligned buffer. The caller must allocate additional storage, following the <b>SCSI_PASS_THROUGH_DIRECT</b> structure, if the caller asks for request-sense data.

### Input Buffer Length
<i>
       Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i>, which must be at least (<i>sense data size</i> + <b>sizeof</b> (<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct.md">SCSI_PASS_THROUGH_DIRECT</a>)). The size of the <b>SCSI_PASS_THROUGH_DIRECT</b> structure is fixed.

### Output Buffer
The port driver returns any request-sense data and the <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct.md">SCSI_PASS_THROUGH_DIRECT</a> structure to the buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i>.

### Output Buffer Length


### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
The <b>Information</b> field is set to the number of bytes returned in the output buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i>. The Status field is set to <b>STATUS_SUCCESS</b>, or possibly to <b>STATUS_BUFFER_TOO_SMALL</b> or <b>STATUS_INVALID_PARAMETER</b> if the input <b>Length</b> value in <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct.md">SCSI_PASS_THROUGH_DIRECT</a> is improperly set or the buffer specifed in  <b>DataBuffer</b> is not properly device aligned.

    ## Remarks
        For data transfer operations, a buffer with alignment  matching the adapter device  is required. Applications can retrieve the device alignment mask by issuing an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> control code request with a query type of <b>PropertyStandardQuery</b> and property id of <b>StorageAdapterProperty</b>. The alignment mask is found in the <b>AlignmentMask</b> member of the <a href="..\ntddstor\ns-ntddstor-_storage_adapter_descriptor.md">STORAGE_ADAPTER_DESCRIPTOR</a> structure that is returned. Drivers may also use the value in the <b>AlignmentMask</b> member of the adapter's <i>DeviceObject</i>.

In the following  example function, a   buffer is prepared as a device  aligned data transfer buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddscsi.h (include Ntddscsi.h) |
| **IRQL** |  |

    ## See Also

        <dl>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a>
</dt>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>
</dt>
<dt>
<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct.md">SCSI_PASS_THROUGH_DIRECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_PASS_THROUGH_DIRECT control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>