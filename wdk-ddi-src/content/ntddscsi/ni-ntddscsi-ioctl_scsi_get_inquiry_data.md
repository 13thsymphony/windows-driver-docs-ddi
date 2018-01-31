---
UID : NI:ntddscsi.IOCTL_SCSI_GET_INQUIRY_DATA
title : IOCTL_SCSI_GET_INQUIRY_DATA
author : windows-driver-content
description : Returns the SCSI inquiry data for all devices on a given SCSI host bus adapter (HBA).
old-location : storage\ioctl_scsi_get_inquiry_data.htm
old-project : storage
ms.assetid : a429061b-ede6-48b1-9fc6-e85e4a7c0dfe
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_scsi_get_inquiry_data, IOCTL_SCSI_GET_INQUIRY_DATA control code [Storage Devices], IOCTL_SCSI_GET_INQUIRY_DATA, ntddscsi/IOCTL_SCSI_GET_INQUIRY_DATA, k307_7565e2a4-7599-4c7e-8da1-24349978627e.xml
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
req.typenames : "*PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE"
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
| **Windows Driver kit version** |  |
| **Header** | ntddscsi.h (include Ntddscsi.h) |
| **IRQL** |  |

## See Also

<a href="..\ntddscsi\ns-ntddscsi-_scsi_adapter_bus_info.md">SCSI_ADAPTER_BUS_INFO</a>

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport.md">IOCTL_SCSI_MINIPORT</a>

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a>

<a href="..\ntddscsi\ns-ntddscsi-_scsi_inquiry_data.md">SCSI_INQUIRY_DATA</a>

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_rescan_bus.md">IOCTL_SCSI_RESCAN_BUS</a>

<a href="..\ntddstor\ns-ntddstor-_storage_device_descriptor.md">STORAGE_DEVICE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_GET_INQUIRY_DATA control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>