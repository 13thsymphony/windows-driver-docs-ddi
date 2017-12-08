---
UID: NS.ntddcdvd._DVD_COPYRIGHT_DESCRIPTOR
title: DVD_COPYRIGHT_DESCRIPTOR
author: windows-driver-content
description: The DVD_COPYRIGHT_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD copyright descriptor.
old-location: storage\dvd_copyright_descriptor.htm
old-project: storage
ms.assetid: e3478867-394b-466c-ad9a-259bedd66669
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: DVD_COPYRIGHT_DESCRIPTOR, DVD_COPYRIGHT_DESCRIPTOR, *PDVD_COPYRIGHT_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DVD_COPYRIGHT_DESCRIPTOR
req.alt-loc: ntddcdvd.h
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

# DVD_COPYRIGHT_DESCRIPTOR structure



## -description
<p>The DVD_COPYRIGHT_DESCRIPTOR structure is used in conjunction with the <a href="..\ntddcdvd\ni-ntddcdvd-ioctl-dvd-read-structure.md">IOCTL_DVD_READ_STRUCTURE</a> request to retrieve a DVD copyright descriptor. </p>


## -syntax

````
typedef struct _DVD_COPYRIGHT_DESCRIPTOR {
  UCHAR  CopyrightProtectionType;
  UCHAR  RegionManagementInformation;
  USHORT Reserved;
} DVD_COPYRIGHT_DESCRIPTOR, *PDVD_COPYRIGHT_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field CopyrightProtectionType

<dd>
<p>Indicates, when set to 1, the presence of data specific to a copyright protection system. A value of zero indicates there is no such data. All other values are reserved.</p>
</dd>

### -field RegionManagementInformation

<dd>
<p>Indicates in which regions of the world the disc can be played. Each bit represents one of eight regions. If a bit is set, the disc cannot be played in the corresponding region. If a bit is not set, the disc can be played in the corresponding region. </p>
</dd>

### -field Reserved

<dd>
<p>Reserved. </p>
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
<dt>Ntddcdvd.h (include Ntddcdvd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddcdvd\ni-ntddcdvd-ioctl-dvd-read-structure.md">IOCTL_DVD_READ_STRUCTURE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DVD_COPYRIGHT_DESCRIPTOR structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
