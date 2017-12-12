---
UID: NI.ks.IOCTL_KS_WRITE_STREAM
title: IOCTL_KS_WRITE_STREAM
author: windows-driver-content
description: An application can use IOCTL_KS_WRITE_STREAM to write data to a pin. The application passes IOCTL_KS_WRITE_STREAM with the parameters described below to the KsSynchronousDeviceControl function.
old-location: stream\ioctl_ks_write_stream.htm
old-project: stream
ms.assetid: 560cfc18-5cbe-4af7-b579-3904ee68acbf
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _KsEdit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_KS_WRITE_STREAM
req.alt-loc: ks.h
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

# IOCTL_KS_WRITE_STREAM IOCTL



## -description
An application can use IOCTL_KS_WRITE_STREAM to write data to a pin. The application passes IOCTL_KS_WRITE_STREAM with the parameters described below to the <a href="stream.kssynchronousdevicecontrol">KsSynchronousDeviceControl</a> function.



## -ioctlparameters

### -input-buffer
A client provides a pointer to an array of <a href="stream.ksstream_header">KSSTREAM_HEADER</a> structures in <b>InBuffer</b>. The stream data to write is contained in the buffers pointed to by the stream headers. The headers can also contain presentation time and duration. 


### -input-buffer-length
The <b>InLength</b> parameter should specify the size, in bytes, of the input buffer contents.


### -output-buffer
Kernel streaming provides the number of bytes written in the <b>BytesReturned</b> parameter.


### -output-buffer-length


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the Status member is set to STATUS_SUCCESS.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\ni-ks-ioctl_ks_read_stream.md">IOCTL_KS_READ_STREAM</a>
</dt>
<dt>
<a href="stream.ksprobestreamirp">KsProbeStreamIrp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IOCTL_KS_WRITE_STREAM control code%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

