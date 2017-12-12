---
UID: NI.ntddscsi.IOCTL_SCSI_GET_INQUIRY_DATA
title: IOCTL_SCSI_GET_INQUIRY_DATA
author: windows-driver-content
description: Returns the SCSI inquiry data for all devices on a given SCSI host bus adapter (HBA).
old-location: storage\ioctl_scsi_get_inquiry_data.htm
old-project: storage
ms.assetid: a429061b-ede6-48b1-9fc6-e85e4a7c0dfe
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
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
req.alt-api: IOCTL_SCSI_GET_INQUIRY_DATA
req.alt-loc: Ntddscsi.h
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
---

# IOCTL_SCSI_GET_INQUIRY_DATA IOCTL



## -description

Returns the SCSI inquiry data for all devices on a given SCSI host bus adapter (HBA). If the IOCTL is employed in user space, the program must have opened a handle to the HBA, which can be enumerated by various means, such as SetupDixxx calls. You can use <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to find information about a specific device on the HBA. To determine the size of the output buffer that is required, the caller should send this IOCTL request in a loop. Every time that the storage stack rejects the IOCTL with an error message that indicates that the buffer was too small, the caller should double the buffer size.



Returns the SCSI inquiry data for all devices on a given SCSI host bus adapter (HBA). If the IOCTL is employed in user space, the program must have opened a handle to the HBA, which can be enumerated by various means, such as SetupDixxx calls. You can use <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to find information about a specific device on the HBA. To determine the size of the output buffer that is required, the caller should send this IOCTL request in a loop. Every time that the storage stack rejects the IOCTL with an error message that indicates that the buffer was too small, the caller should double the buffer size.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the returned inquiry data. For a description of the layout of the inquiry data in the output buffer, see <a href="storage.scsi_adapter_bus_info">SCSI_ADAPTER_BUS_INFO</a>.


### -output-buffer-length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the buffer, which must be &gt;= (<b>sizeof</b>(SCSI_ADAPTER_BUS_INFO) + (<i>NumberOfBuses</i>) * <b>sizeof</b>(SCSI_BUS_DATA)) + (<i>InquiryDataSize</i> * <i>NumberOfLUs</i>), where the <i>InquiryDataSize</i> is (<b>sizeof</b>(SCSI_INQUIRY_DATA) - 1 + INQUIRYDATABUFFERSIZE) rounded up to an alignment boundary.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddscsi.h (include Ntddscsi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport.md">IOCTL_SCSI_MINIPORT</a>
</dt>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a>
</dt>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>
</dt>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_rescan_bus.md">IOCTL_SCSI_RESCAN_BUS</a>
</dt>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>
</dt>
<dt>
<a href="storage.scsi_adapter_bus_info">SCSI_ADAPTER_BUS_INFO</a>
</dt>
<dt>
<a href="storage.scsi_inquiry_data">SCSI_INQUIRY_DATA</a>
</dt>
<dt>
<a href="storage.storage_device_descriptor">STORAGE_DEVICE_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_GET_INQUIRY_DATA control code%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

