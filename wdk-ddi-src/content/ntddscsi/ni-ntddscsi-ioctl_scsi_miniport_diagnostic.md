---
UID: NI.ntddscsi.IOCTL_SCSI_MINIPORT_DIAGNOSTIC
title: IOCTL_SCSI_MINIPORT_DIAGNOSTIC
author: windows-driver-content
description: The IOCTL_SCSI_MINIPORT_DIAGNOSTIC control code is use to perform a diagnostic request to the Miniport.
old-location: storage\ioctl_scsi_miniport_diagnostic.htm
old-project: storage
ms.assetid: 79E89E4A-3B06-40FA-BFA6-598331C0A330
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SCSI_MINIPORT_DIAGNOSTIC
req.alt-loc: ntddscsi.h
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

# IOCTL_SCSI_MINIPORT_DIAGNOSTIC IOCTL



## -description
The <b>IOCTL_SCSI_MINIPORT_DIAGNOSTIC</b> 
   control code is use to perform a diagnostic request to the Miniport.



## -ioctlparameters

### -input-buffer

<text></text>

### -input-buffer-length

<text></text>

### -output-buffer

<text></text>

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks
To perform this operation, call the <a href="base.deviceiocontrol">DeviceIoControl</a> 
   function with the following parameters.


<pre class="syntax">BOOL 
   WINAPI 
   DeviceIoControl( (HANDLE)       hDevice,         // handle to device
                    (DWORD)        IOCTL_SCSI_MINIPORT_DIAGNOSTIC, // dwIoControlCode
                    (LPDWORD)      lpInBuffer,      // input buffer
                    (DWORD)        nInBufferSize,   // size of input buffer
                    (LPDWORD)      lpOutBuffer,     // output buffer
                    (DWORD)        nOutBufferSize,  // size of output buffer
                    (LPDWORD)      lpBytesReturned, // number of bytes returned
                    (LPOVERLAPPED) lpOverlapped );  // OVERLAPPED structure</pre>



Parameters



Parameters


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddscsi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.storage_diagnostic_mp_request">STORAGE_DIAGNOSTIC_MP_REQUEST</a>
</dt>
<dt>
<a href="base.deviceiocontrol">DeviceIoControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_MINIPORT_DIAGNOSTIC control code%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

