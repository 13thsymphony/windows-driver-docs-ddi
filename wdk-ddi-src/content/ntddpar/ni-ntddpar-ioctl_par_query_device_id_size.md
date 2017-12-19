---
UID: NI.ntddpar.IOCTL_PAR_QUERY_DEVICE_ID_SIZE
title: IOCTL_PAR_QUERY_DEVICE_ID_SIZE
author: windows-driver-content
description: The IOCTL_PAR_QUERY_DEVICE_ID_SIZE request returns the size, in bytes, of a buffer that can hold a device's IEEE 1284 device ID and a NULL terminator.
old-location: parports\ioctl_par_query_device_id_size.htm
old-project: parports
ms.assetid: f593e36e-8c2b-4cdc-ade1-d1e260f37667
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION, OFFLOAD_SECURITY_ASSOCIATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddpar.h
req.include-header: Ntddpar.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_PAR_QUERY_DEVICE_ID_SIZE
req.alt-loc: ntddpar.h
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

# IOCTL_PAR_QUERY_DEVICE_ID_SIZE IOCTL



## -description

The IOCTL_PAR_QUERY_DEVICE_ID_SIZE request returns the size, in bytes, of a buffer that can hold a device's IEEE 1284 device ID and a <b>NULL</b> terminator.



The IOCTL_PAR_QUERY_DEVICE_ID_SIZE request returns the size, in bytes, of a buffer that can hold a device's IEEE 1284 device ID and a <b>NULL</b> terminator.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="parports.par_device_id_size_information">PAR_DEVICE_ID_SIZE_INFORMATION</a> structure that the client allocates to output the device ID size information. The system-supplied bus driver for parallel ports sets the <b>DeviceIdSize</b> member of the output structure to the size, in bytes, of a buffer that can hold the device ID and a <b>NULL</b> terminator.


### -output-buffer-length
The length of a <a href="parports.par_device_id_size_information">PAR_DEVICE_ID_SIZE_INFORMATION</a> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a PAR_DEVICE_ID_SIZE_INFORMATION structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to STATUS_IO_DEVICE_ERROR


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddpar.h (include Ntddpar.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id.md">IOCTL_PAR_QUERY_DEVICE_ID</a>
</dt>
<dt>
<a href="parports.par_device_id_size_information">PAR_DEVICE_ID_SIZE_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_PAR_QUERY_DEVICE_ID_SIZE control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

