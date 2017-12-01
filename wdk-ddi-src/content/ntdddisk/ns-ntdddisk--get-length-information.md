---
UID: NS.ntdddisk._GET_LENGTH_INFORMATION
title: GET_LENGTH_INFORMATION
author: windows-driver-content
description: The GET_LENGTH_INFORMATION structure is used with the IOCTL_DISK_GET_LENGTH_INFO to obtain the length, in bytes, of a disk, partition, or volume.
old-location: storage\get_length_information.htm
old-project: storage
ms.assetid: 1c5af24f-fd99-4a64-afd4-aaa8168b1dc5
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: GET_LENGTH_INFORMATION, GET_LENGTH_INFORMATION, *PGET_LENGTH_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GET_LENGTH_INFORMATION
req.alt-loc: ntdddisk.h
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
req.iface: 
---

# GET_LENGTH_INFORMATION structure



## -description
<p>The GET_LENGTH_INFORMATION structure is used with the <a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-get-length-info.md">IOCTL_DISK_GET_LENGTH_INFO</a> to obtain the length, in bytes, of a disk, partition, or volume. </p>


## -syntax

````
typedef struct _GET_LENGTH_INFORMATION {
  LARGE_INTEGER Length;
} GET_LENGTH_INFORMATION, *PGET_LENGTH_INFORMATION;
````


## -struct-fields
<dl>

### -field <b>Length</b>

<dd>
<p>Contains the length, in bytes, of a disk, partition, or volume.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntdddisk.h (include Ntdddisk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-get-length-info.md">IOCTL_DISK_GET_LENGTH_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GET_LENGTH_INFORMATION structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
