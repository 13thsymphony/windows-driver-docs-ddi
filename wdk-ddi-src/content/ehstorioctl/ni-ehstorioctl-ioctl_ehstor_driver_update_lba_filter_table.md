---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE
title: IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE
author: windows-driver-content
description: This IOCTL is used to inform the enhanced storage (EHSTOR) class driver of changes to the LBA filter table.
old-location: storage\ioctl_ehstor_driver_update_lba_filter_table.htm
old-project: storage
ms.assetid: 295EE3CC-4244-4411-9684-7C5D38B10EA9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE, IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE, storage.ioctl_ehstor_driver_update_lba_filter_table
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
-	EhStorIoctl.h
api_name:
-	IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE
product: Windows
targetos: Windows
req.typenames: PDO_TYPE
---

# IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE IOCTL
This IOCTL is used to inform the enhanced storage (EHSTOR) class driver of changes to the LBA filter table. Bands managed by the silo  driver are composed of LBA ranges. The silo driver notifies the EHSTOR class driver of updates to the set of  bands it controls with this IOCTL.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The input buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> must contain a structure of type <a href="..\ehstorioctl\ns-ehstorioctl-_lba_filter_table.md">LBA_FILTER_TABLE</a>. This structure contains the filter table and the total entries it contains. An array <a href="..\ehstorioctl\ns-ehstorioctl-_lba_filter_table_entry.md">LBA_FILTER_TABLE_ENTRY</a> structure follows <b>LBA_FILTER_TABLE</b>.

### Input Buffer Length
The length of the buffer.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
One of the following values can be returned in the <b>Status</b> field.

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>The LBA filter table was successfully updated.</td>
</tr>
<tr>
<td>STATUS_INVALID_BUFFER_SIZE</td>
<td>The input buffer length supplied is of incorrect size.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>The LBA filter count or an LBA range is specified incorrectly.</td>
</tr>
<tr>
<td>STATUS_INSUFFICIENT_RESOURCES</td>
<td>The IOCTL redirection list cannot be copied.</td>
</tr>
<tr>
<td>STATUS_NOT_SUPPORTED</td>
<td>The sending device is not a silo device or banding is not supported.</td>
</tr>
</table>

## Remarks
The LBA filters cannot overlap or be empty. The LBA filters do not have to be sorted in any way. 

If an LBA range is being unlocked, an <b>IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</b> request should be sent after the LBA range is unlocked on the storage device. Also,
 if an LBA range is currently being locked, <b>IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</b>  must be sent before the LBA range has been locked on the storage device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8 Available starting with Windows 8 |
| **Header** | ehstorioctl.h (include EhStorIoctl.h) |

## See Also

<a href="..\ehstorioctl\ns-ehstorioctl-_lba_filter_table_entry.md">LBA_FILTER_TABLE_ENTRY</a>



<a href="..\ehstorioctl\ns-ehstorioctl-_lba_filter_table.md">LBA_FILTER_TABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>