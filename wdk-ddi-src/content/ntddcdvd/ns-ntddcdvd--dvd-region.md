---
UID: NS.ntddcdvd._DVD_REGION
title: DVD_REGION
author: windows-driver-content
description: The DVD_REGION structure is used in conjunction with the IOCTL_DVD_GET_REGION request to retrieve region playback control (RPC) information for a DVD device.
old-location: storage\dvd_region.htm
old-project: storage
ms.assetid: a2e31a1a-59e4-4a83-b866-944ef1693f65
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: DVD_REGION, DVD_REGION, *PDVD_REGION
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
req.alt-api: DVD_REGION
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

# DVD_REGION structure



## -description
<p>The DVD_REGION structure is used in conjunction with the <a href="..\ntddcdvd\ni-ntddcdvd-ioctl-dvd-get-region.md">IOCTL_DVD_GET_REGION</a> request to retrieve region playback control (RPC) information for a DVD device.</p>


## -syntax

````
typedef struct _DVD_REGION {
  UCHAR CopySystem;
  UCHAR RegionData;
  UCHAR SystemRegion;
  UCHAR ResetCount;
} DVD_REGION, *PDVD_REGION;
````


## -struct-fields
<dl>

### -field CopySystem

<dd>
<p>Indicates the copyright protection type. For more information about copyright protection types, see the <i>SCSI Multimedia Commands - 3</i> (MMC-3) specification.</p>
</dd>

### -field RegionData

<dd>
<p>Indicates the region code of the currently mounted DVD media. This is an eight-bit bitmask, with one bit for each DVD region. A value of 0x00 means that no region is specified. </p>
</dd>

### -field SystemRegion

<dd>
<p>Indicates the region code of the DVD player. This is an eight-bit bitmask, with one bit for each system region. A value of 0x00 means that no region is specified. </p>
</dd>

### -field ResetCount

<dd>
<p>Indicates the remaining number of times the DVD device's region code can be changed by the user. This member can hold a value between 0 and 7.</p>
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
<a href="..\ntddcdvd\ni-ntddcdvd-ioctl-dvd-get-region.md">IOCTL_DVD_GET_REGION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DVD_REGION structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
