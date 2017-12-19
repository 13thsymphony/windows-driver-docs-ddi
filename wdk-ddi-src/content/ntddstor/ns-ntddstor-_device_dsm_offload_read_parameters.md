---
UID: NS.NTDDSTOR._DEVICE_DSM_OFFLOAD_READ_PARAMETERS
title: _DEVICE_DSM_OFFLOAD_READ_PARAMETERS
author: windows-driver-content
description: The DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure specifies the parameters for an offload read action related to the data-set attributes for a device.
old-location: storage\device_dsm_offload_read_parameters.htm
old-project: storage
ms.assetid: 4C0B2CFD-B981-4304-B3F9-AD534BF5A823
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DEVICE_DSM_OFFLOAD_READ_PARAMETERS, DEVICE_DSM_OFFLOAD_READ_PARAMETERS, PDEVICE_DSM_OFFLOAD_READ_PARAMETERS, *PDEVICE_DSM_OFFLOAD_READ_PARAMETERS
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
req.alt-api: DEVICE_DSM_OFFLOAD_READ_PARAMETERS
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
---

# _DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure



## -description
The <b>DEVICE_DSM_OFFLOAD_READ_PARAMETERS</b> structure specifies the parameters for an offload read action related to the data-set attributes for a device. 

This parameter structure is used in an offload read  action for an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.  The <b>Action</b> member of the <a href="storage.device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure is set to <b>DeviceDsmAction_OffloadRead</b>, and <b>ParameterBlockOffset</b> indicates the location of <b>DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</b>.



## -syntax

````
typedef struct _DEVICE_DSM_OFFLOAD_READ_PARAMETERS {
  ULONG Flags;
  ULONG TimeToLive;
  ULONG Reserved[2];
} DEVICE_DSM_OFFLOAD_READ_PARAMETERS, *PDEVICE_DSM_OFFLOAD_READ_PARAMETERS;
````


## -struct-fields

### -field Flags

Not used. Set to 0.


### -field TimeToLive

The duration, in milliseconds, for which the requested data ranges should remain valid.


### -field Reserved

Reserved.


## -remarks
The <b>ParameterBlockOffset</b> and <b>ParameterBlockLength</b> members  of <a href="storage.device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> are set to the location and length of the  <b>DEVICE_DSM_OFFLOAD_READ_PARAMETERS</b> structure in the system buffer of the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.

The <b>DataSetRangesOffset</b> and <b>DataSetRangesLength</b> members of <a href="storage.device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> specify the <a href="storage.device_data_set_range">DEVICE_DATA_SET_RANGE</a> structures for the extents of the offload read.


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
<a href="storage.device_data_set_range">DEVICE_DATA_SET_RANGE</a>
</dt>
<dt>
<a href="storage.device_dsm_offload_write_parameters">DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</a>
</dt>
<dt>
<a href="storage.device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

