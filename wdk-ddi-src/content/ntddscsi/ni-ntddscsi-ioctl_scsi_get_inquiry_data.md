---
UID: NI:ntddscsi.IOCTL_SCSI_GET_INQUIRY_DATA
title: IOCTL_SCSI_GET_INQUIRY_DATA
author: windows-driver-content
description: Returns the SCSI inquiry data for all devices on a given SCSI host bus adapter (HBA).
old-location: storage\ioctl_scsi_get_inquiry_data.htm
old-project: storage
ms.assetid: a429061b-ede6-48b1-9fc6-e85e4a7c0dfe
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_SCSI_GET_INQUIRY_DATA, IOCTL_SCSI_GET_INQUIRY_DATA control code [Storage Devices], k307_7565e2a4-7599-4c7e-8da1-24349978627e.xml, ntddscsi/IOCTL_SCSI_GET_INQUIRY_DATA, storage.ioctl_scsi_get_inquiry_data
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
-	IOCTL_SCSI_GET_INQUIRY_DATA
product: Windows
targetos: Windows
req.typenames: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_SCSI_GET_INQUIRY_DATA IOCTL
Returns the SCSI inquiry data for all devices on a given SCSI host bus adapter (HBA). If the IOCTL is employed in user space, the program must have opened a handle to the HBA, which can be enumerated by various means, such as SetupDixxx calls. You can use <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to find information about a specific device on the HBA. To determine the size of the output buffer that is required, the caller should send this IOCTL request in a loop. Every time that the storage stack rejects the IOCTL with an error message that indicates that the buffer was too small, the caller should double the buffer size.


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the returned inquiry data. For a description of the layout of the inquiry data in the output buffer, see <a href="..\ntddscsi\ns-ntddscsi-_scsi_adapter_bus_info.md">SCSI_ADAPTER_BUS_INFO</a>.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the buffer, which must be &gt;= (<b>sizeof</b>(SCSI_ADAPTER_BUS_INFO) + (<i>NumberOfBuses</i>) * <b>sizeof</b>(SCSI_BUS_DATA)) + (<i>InquiryDataSize</i> * <i>NumberOfLUs</i>), where the <i>InquiryDataSize</i> is (<b>sizeof</b>(SCSI_INQUIRY_DATA) - 1 + INQUIRYDATABUFFERSIZE) rounded up to an alignment boundary.

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

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_rescan_bus.md">IOCTL_SCSI_RESCAN_BUS</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport.md">IOCTL_SCSI_MINIPORT</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_inquiry_data.md">SCSI_INQUIRY_DATA</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_adapter_bus_info.md">SCSI_ADAPTER_BUS_INFO</a>



<a href="..\ntddstor\ns-ntddstor-_storage_device_descriptor.md">STORAGE_DEVICE_DESCRIPTOR</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>