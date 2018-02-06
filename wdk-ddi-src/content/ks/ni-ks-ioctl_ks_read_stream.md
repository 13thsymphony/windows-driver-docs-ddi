---
UID: NI:ks.IOCTL_KS_READ_STREAM
title: IOCTL_KS_READ_STREAM
author: windows-driver-content
description: An application can use IOCTL_KS_READ_STREAM to read data from a pin. The application passes IOCTL_KS_READ_STREAM with the parameters described below to the KsSynchronousDeviceControl function.
old-location: stream\ioctl_ks_read_stream.htm
old-project: stream
ms.assetid: 92110e27-5f1a-4c4d-b999-d9deb546e6a6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ioctl_ks_read_stream, IOCTL_KS_READ_STREAM control code [Streaming Media Devices], IOCTL_KS_READ_STREAM, ks/IOCTL_KS_READ_STREAM, ks-ioctl_677f9dd3-bd4b-4c15-8ee1-67ede429c958.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	IOCTL_KS_READ_STREAM
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_READ_STREAM IOCTL
An application can use IOCTL_KS_READ_STREAM to read data from a pin. The application passes IOCTL_KS_READ_STREAM with the parameters described below to the <a href="..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md">KsSynchronousDeviceControl</a> function.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The application places a pointer to an array of <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a> structures in the <b>InBuffer</b> parameter. Each describes a packet of data to be read. The headers can also contain the presentation time and duration.

### Input Buffer Length
The <b>InLength</b> parameter specifies the size, in bytes, of the input buffer contents.

### Output Buffer
Stream data is returned in the buffers pointed to by the stream headers.  Upon return, <b>BytesReturned</b> contains the number of bytes read.

### Output Buffer Length
<b>OutLength</b> specifies the size, in bytes, of the output buffer contents.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the Status member is set to STATUS_SUCCESS.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ni-ks-ioctl_ks_write_stream.md">IOCTL_KS_WRITE_STREAM</a>

<a href="..\ks\nf-ks-ksprobestreamirp.md">KsProbeStreamIrp</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IOCTL_KS_READ_STREAM control code%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>