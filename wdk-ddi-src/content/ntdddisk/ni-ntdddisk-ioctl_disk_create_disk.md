---
UID: NI.ntdddisk.IOCTL_DISK_CREATE_DISK
title: IOCTL_DISK_CREATE_DISK
author: windows-driver-content
description: Creates an empty partition for the device object.
old-location: storage\ioctl_disk_create_disk.htm
old-project: storage
ms.assetid: 9ec6835c-43b8-4878-9ddf-1ca7c24435c2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DETECTION_TYPE, DETECTION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_DISK_CREATE_DISK
req.alt-loc: Ntdddisk.h
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

# IOCTL_DISK_CREATE_DISK IOCTL



## -description

Creates an empty partition for the device object. It can operate on either an EFI disk or an MBR disk. The parameters necessary to create an empty disk depend on the type of partition table that will be put onto the disk. For more information, see <a href="storage.create_disk">CREATE_DISK</a>.

Disk drivers enumerate partitions as though they were child devices. Thus, upon creating the new partition, the disk class driver notifies the PnP manager by means of a call to <b>IoInvalidateDeviceRelations</b> that the disk device has a new child device (partition).



Creates an empty partition for the device object. It can operate on either an EFI disk or an MBR disk. The parameters necessary to create an empty disk depend on the type of partition table that will be put onto the disk. For more information, see <a href="storage.create_disk">CREATE_DISK</a>.

Disk drivers enumerate partitions as though they were child devices. Thus, upon creating the new partition, the disk class driver notifies the PnP manager by means of a call to <b>IoInvalidateDeviceRelations</b> that the disk device has a new child device (partition).



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the CREATE_DISK data. 


### -input-buffer-length
<b>
       Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be &gt;= <b>sizeof</b>(CREATE_DISK). Otherwise, the driver returns with an error status of STATUS_INFO_LENGTH_MISMATCH.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS if the operation was successful. Other possible status values are: STATUS_NOT_SUPPORTED if the partition style requested is not supported; STATUS_DEVICE_NOT_READY if the class driver failed to retrieve the disk geometry; and STATUS_INSUFFICIENT_RESOURCES if the class driver failed to obtain a necessary resource, such as heap memory.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntdddisk.h (include Ntdddisk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.create_disk">CREATE_DISK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_CREATE_DISK control code%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

