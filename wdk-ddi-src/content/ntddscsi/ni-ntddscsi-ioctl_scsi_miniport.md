---
UID: NI.ntddscsi.IOCTL_SCSI_MINIPORT
title: IOCTL_SCSI_MINIPORT
author: windows-driver-content
description: Sends a special control function to an HBA-specific miniport driver.
old-location: storage\ioctl_scsi_miniport.htm
old-project: storage
ms.assetid: 5a9facc7-c83e-4dd4-9fb4-e3385c1b94ea
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
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
req.alt-api: IOCTL_SCSI_MINIPORT
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

# IOCTL_SCSI_MINIPORT IOCTL



## -description

Sends a special control function to an HBA-specific miniport driver. Results vary, depending on the particular miniport driver to which this request is forwarded. If the caller specifies a nonzero <b>Length</b>, either the input or output buffer must be at least (<b>sizeof</b>(SRB_IO_CONTROL) + <i>DataBufferLength</i>)).



Sends a special control function to an HBA-specific miniport driver. Results vary, depending on the particular miniport driver to which this request is forwarded. If the caller specifies a nonzero <b>Length</b>, either the input or output buffer must be at least (<b>sizeof</b>(SRB_IO_CONTROL) + <i>DataBufferLength</i>)).



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> must contain an <a href="storage.srb_io_control">SRB_IO_CONTROL</a> structure. 


### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b>(SRB_IO_CONTROL), with additional storage for data if the <b>Length</b> field is nonzero.


### -output-buffer
An updated <a href="storage.srb_io_control">SRB_IO_CONTROL</a> structure is returned to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length
The length of the <a href="storage.srb_io_control">SRB_IO_CONTROL</a> structure.


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
<a href="storage.srb_io_control">SRB_IO_CONTROL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_MINIPORT control code%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

