---
UID: NI:ntddscsi.IOCTL_SCSI_GET_CAPABILITIES
title: IOCTL_SCSI_GET_CAPABILITIES
author: windows-driver-content
description: Returns the capabilities and limitations of the underlying SCSI HBA.
old-location: storage\ioctl_scsi_get_capabilities.htm
old-project: storage
ms.assetid: 1917e0f0-47a3-4f95-97d6-c60d3f511a91
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_scsi_get_capabilities, IOCTL_SCSI_GET_CAPABILITIES control code [Storage Devices], IOCTL_SCSI_GET_CAPABILITIES, ntddscsi/IOCTL_SCSI_GET_CAPABILITIES, k307_99c3b622-6b7f-4550-9740-22b46d141966.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddscsi.h
apiname:
-	IOCTL_SCSI_GET_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: "*PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE"
---

# IOCTL_SCSI_GET_CAPABILITIES IOCTL
Returns the capabilities and limitations of the underlying SCSI HBA. The most important information is returned in the <b>MaximumTransferLength</b> and <b>AlignmentMask </b>members. Class drivers and users of <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a> and <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a> are required to honor these limitations.

Only legacy drivers can issue this request. The request fails if it is sent to a PDO created by the port driver. 

To get SCSI capabilities data, a Plug and Play driver must issue an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request for <a href="..\ntddstor\ns-ntddstor-_storage_adapter_descriptor.md">STORAGE_ADAPTER_DESCRIPTOR</a> data to the PDO for each device to which the driver has been added (that is, each device for which the driver has received an <i>AddDevice </i>call). A legacy driver should forward this request to the port driver. This request fails if it is sent to the FDO for an adapter.


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
Updated <a href="..\ntddscsi\ns-ntddscsi-_io_scsi_capabilities.md">IO_SCSI_CAPABILITIES</a> information is returned to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(IO_SCSI_CAPABILITIES).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="..\ntddscsi\ns-ntddscsi-_io_scsi_capabilities.md">IO_SCSI_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_GET_CAPABILITIES control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>