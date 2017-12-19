---
UID: NI.ntddtape.IOCTL_TAPE_GET_MEDIA_PARAMS
title: IOCTL_TAPE_GET_MEDIA_PARAMS
author: windows-driver-content
description: Returns information about the media's total and remaining capacity, its block size, the number of partitions, and whether it is write-protected.
old-location: storage\ioctl_tape_get_media_params.htm
old-project: storage
ms.assetid: 4fd09b30-d63b-4b7f-9f6c-ef028e5e549f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _TAPE_DRIVE_PROBLEM_TYPE, TAPE_DRIVE_PROBLEM_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddtape.h
req.include-header: Ntddtape.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_TAPE_GET_MEDIA_PARAMS
req.alt-loc: Ntddtape.h
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

# IOCTL_TAPE_GET_MEDIA_PARAMS IOCTL



## -description

Returns information about the media's total and remaining capacity, its block size, the number of partitions, and whether it is write-protected.



Returns information about the media's total and remaining capacity, its block size, the number of partitions, and whether it is write-protected.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The driver returns the <a href="storage.tape_get_media_parameters">TAPE_GET_MEDIA_PARAMETERS</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. For a description of the TAPE_GET_MEDIA_PARAMETERS structure, see <a href="storage.tapeminigetmediaparameters">TapeMiniGetMediaParameters</a>.


### -output-buffer-length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_GET_MEDIA_PARAMETERS).


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_IO_DEVICE_ERROR, STATUS_DEVICE_DATA_ERROR, STATUS_DATA_OVERRUN, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_INFO_LENGTH_MISMATCH, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddtape.h (include Ntddtape.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.tape_get_media_parameters">TAPE_GET_MEDIA_PARAMETERS</a>
</dt>
<dt>
<a href="storage.tapeminigetmediaparameters">TapeMiniGetMediaParameters</a>
</dt>
<dt>
<a href="storage.tape_status">TAPE_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_TAPE_GET_MEDIA_PARAMS control code%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

