---
UID: NI.ntddtape.IOCTL_TAPE_SET_DRIVE_PARAMS
title: IOCTL_TAPE_SET_DRIVE_PARAMS
author: windows-driver-content
description: Adjusts a tape drive's configurable parameters.
old-location: storage\ioctl_tape_set_drive_params.htm
old-project: storage
ms.assetid: aa625cbf-fa0f-420a-b8ec-2babf4c4ec17
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
req.alt-api: IOCTL_TAPE_SET_DRIVE_PARAMS
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

# IOCTL_TAPE_SET_DRIVE_PARAMS IOCTL



## -description

Adjusts a tape drive's configurable parameters. The miniclass driver can ignore parameters that its device does not support. The calling application is responsible for determining whether a device supports a particular feature before attempting to set it.



Adjusts a tape drive's configurable parameters. The miniclass driver can ignore parameters that its device does not support. The calling application is responsible for determining whether a device supports a particular feature before attempting to set it.



## -ioctlparameters

### -input-buffer

       The <a href="storage.tape_set_drive_parameters">TAPE_SET_DRIVE_PARAMETERS</a> structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the values to be set. 


### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_SET_DRIVE_PARAMETERS). 


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
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_IO_DEVICE_ERROR, STATUS_INVALID_DEVICE_REQUEST, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_INFO_LENGTH_MISMATCH, or STATUS_DEVICE_NOT_READY.


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
<a href="storage.tape_set_drive_parameters">TAPE_SET_DRIVE_PARAMETERS</a>
</dt>
<dt>
<a href="storage.tapeminisetdriveparameters">TapeMiniSetDriveParameters</a>
</dt>
<dt>
<a href="storage.tape_status">TAPE_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_TAPE_SET_DRIVE_PARAMS control code%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

