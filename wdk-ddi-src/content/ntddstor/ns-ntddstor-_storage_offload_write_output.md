---
UID: NS:ntddstor._STORAGE_OFFLOAD_WRITE_OUTPUT
title: _STORAGE_OFFLOAD_WRITE_OUTPUT
author: windows-driver-content
description: The STORAGE_OFFLOAD_WRITE_OUTPUT structure is the output of an IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code request when the Action member of DEVICE_MANAGE_DATA_SET_ATTRIBUTES is set to DeviceDsmAction_OffloadWrite.
old-location: storage\storage_offload_write_output.htm
old-project: storage
ms.assetid: 95EF1722-5171-4A09-8676-7910E53E3868
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_OFFLOAD_WRITE_OUTPUT, *PSTORAGE_OFFLOAD_WRITE_OUTPUT, STORAGE_OFFLOAD_WRITE_OUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_OFFLOAD_WRITE_OUTPUT
req.alt-loc: ntddstor.h
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
req.typenames: *PSTORAGE_OFFLOAD_WRITE_OUTPUT, STORAGE_OFFLOAD_WRITE_OUTPUT
---

# _STORAGE_OFFLOAD_WRITE_OUTPUT structure



## -description
The <b>STORAGE_OFFLOAD_WRITE_OUTPUT</b> structure is the output of  an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> control code request when the <b>Action</b> member of <a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> is set to <b>DeviceDsmAction_OffloadWrite</b>.

On input, a token value in <a href="..\ntddstor\ns-ntddstor-_device_dsm_offload_write_parameters.md">DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</a> uniquely identifies the data set ranges requested for writing in the <a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure. The <b>STORAGE_OFFLOAD_WRITE_OUTPUT</b> structure contains the results of the write operation.



## -syntax

````
typedef struct _STORAGE_OFFLOAD_WRITE_OUTPUT {
  ULONG     OffloadWriteFlags;
  ULONG     Reserved;
  ULONGLONG LengthCopied;
} STORAGE_OFFLOAD_WRITE_OUTPUT, *PSTORAGE_OFFLOAD_WRITE_OUTPUT;
````


## -struct-fields

### -field OffloadWriteFlags

Flags indicating the result of the offload write operation. This is set to one of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field STORAGE_OFFLOAD_WRITE_RANGE_TRUNCATED

</td>
<td width="60%">
The offload write was performed but the range written was truncated.

</td>
</tr>
<tr>

### -field STORAGE_OFFLOAD_TOKEN_INVALID         

</td>
<td width="60%">
The token provided for the offload write operation was invalid.

</td>
</tr>
</table>
 


### -field Reserved

Reserved.


### -field LengthCopied

Bytes copied for the write request in <a href="..\ntddstor\ns-ntddstor-_device_dsm_offload_write_parameters.md">DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</a>.


## -remarks
The <b>STORAGE_OFFLOAD_WRITE_OUTPUT</b> structure is returned at the beginning of the system buffer.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 8 and later versions of Windows.

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
<a href="..\ntddstor\ns-ntddstor-_device_dsm_offload_write_parameters.md">DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_OFFLOAD_WRITE_OUTPUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

