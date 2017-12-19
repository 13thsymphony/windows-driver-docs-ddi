---
UID: NI.ntddstor.IOCTL_STORAGE_FIRMWARE_DOWNLOAD
title: IOCTL_STORAGE_FIRMWARE_DOWNLOAD
author: windows-driver-content
description: A driver can use IOCTL_STORAGE_FIRMWARE_DOWNLOAD to download a firmware image to a storage device, but does not activate it.
old-location: storage\ioctl_storage_firmware_download.htm
old-project: storage
ms.assetid: D5572EE3-C277-494C-B288-A6E8F8A26A3E
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STORAGE_ZONE_CONDITION, PSTORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_STORAGE_FIRMWARE_DOWNLOAD
req.alt-loc: Ntddstor.h
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

# IOCTL_STORAGE_FIRMWARE_DOWNLOAD IOCTL



## -description
A driver can use <b>IOCTL_STORAGE_FIRMWARE_DOWNLOAD</b> to download a firmware image to a storage device, but does not activate it. If the image to be downloaded is larger than the controller’s maximum data transfer size, this IOCTL will have to be called multiple times until the entire image is downloaded.



## -ioctlparameters

### -input-buffer
<b>
       Irp-&gt;AssociatedIrp.SystemBuffer</b> contains <a href="storage.storage_hw_firmware_download">STORAGE_HW_FIRMWARE_DOWNLOAD</a> data that specifies information about the downloaded firmware to activate.


### -input-buffer-length
<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the parameter buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be &gt;= <b>sizeof</b>(<a href="storage.storage_hw_firmware_download">STORAGE_HW_FIRMWARE_DOWNLOAD</a>).


### -output-buffer
This IOCTL has no output structure.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to <b>STATUS_SUCCESS</b>, or possibly to <b>STATUS_INSUFFICIENT_RESOURCES</b>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.storage_hw_firmware_download">STORAGE_HW_FIRMWARE_DOWNLOAD</a>
</dt>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_firmware_activate.md">IOCTL_STORAGE_FIRMWARE_ACTIVATE</a>
</dt>
<dt>
<a href="storage.storage_hw_firmware_activate">STORAGE_HW_FIRMWARE_ACTIVATE</a>
</dt>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_firmware_get_info.md">IOCTL_STORAGE_FIRMWARE_GET_INFO</a>
</dt>
<dt>
<a href="storage.storage_hw_firmware_info">STORAGE_HW_FIRMWARE_INFO</a>
</dt>
<dt>
<a href="storage.storage_hw_firmware_info_query">STORAGE_HW_FIRMWARE_INFO_QUERY</a>
</dt>
<dt>
<a href="storage.storage_hw_firmware_slot_info">STORAGE_HW_FIRMWARE_SLOT_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_FIRMWARE_DOWNLOAD control code%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

