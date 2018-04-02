---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA
title: IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA
author: windows-driver-content
description: Metadata associated with a band is set with an IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA request. The metadata for a band serves as a data area for a key manager application.
old-location: storage\ioctl_ehstor_bandmgmt_set_band_metadata.htm
old-project: storage
ms.assetid: 5FBEAB29-C256-47EF-B673-6584679B8908
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA, IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA, storage.ioctl_ehstor_bandmgmt_set_band_metadata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
-	EhStorBandMgmt.h
api_name:
-	IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA
product: Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA IOCTL
Metadata associated with a band is set with an <b>IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</b> request. The metadata for a band serves as a data area for a key manager application.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The input buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> must contain a <a href="https://msdn.microsoft.com/library/windows/hardware/hh464115">SET_BAND_METADATA_PARAMETERS</a> and possibly an <b>AUTH_KEY</b> structure along with the new metadata to set for the band. 

If the <b>AuthKeyOffset</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh464115">SET_BAND_METADATA_PARAMETERS</a> is set to <b>EHSTOR_BANDMGR_NO_KEY</b>, the input data in the system buffer need not include an <b>AUTH_KEY</b> structure.

### Input Buffer Length
<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (SET_BAND_METADATA_PARAMETERS)    + <b>MetadataSize</b> + <b>sizeof</b>(AUTH_KEY).

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
One of the following values may be returned in the <b>Status</b> field: 

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>The metadata was set for the selected band.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_REQUEST</td>
<td>Storage device does not support band management.</td>
</tr>
<tr>
<td>STATUS_INVALID_BUFFER_SIZE</td>
<td>The input buffer size is incorrect.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>Information in the input buffer is invalid.</td>
</tr>
<tr>
<td>STATUS_NOT_FOUND</td>
<td>Band was not found for the selection criteria provided.</td>
</tr>
<tr>
<td>STATUS_IO_DEVICE_ERROR</td>
<td>Communication failed. The storage device might be incompatible with security protocols. </td>
</tr>
</table>

## Remarks
Metadata can also be erased by using this IOCTL. To erase metadata for a band, set the metadata portion of input buffer to all zeros or some other erase pattern. To ensure removal of sensitive information in metadata blobs, this erase operation should be performed prior to deleting a band from the silo driver's band table.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 8 and later versions of Windows. Available in Windows 8 and later versions of Windows. |
| **Header** | ehstorbandmgmt.h (include EhStorBandMgmt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh464115">SET_BAND_METADATA_PARAMETERS</a>