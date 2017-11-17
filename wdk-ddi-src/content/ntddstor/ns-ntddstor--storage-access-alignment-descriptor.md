---
UID: NS.ntddstor._STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
title: STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
author: windows-driver-content
description: The STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the storage access alignment descriptor data for a device.
old-location: storage\storage_access_alignment_descriptor.htm
ms.assetid: 988122bf-d7de-44a3-a059-c984bf636cd0
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
req.alt-loc: ntddstor.h
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
ms.keywords: STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, *PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
req.iface: 
---

# STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure



## -description
<p>The STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the storage access alignment descriptor data for a device. </p>


## -syntax

````
typedef struct _STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR {
  ULONG Version;
  ULONG Size;
  ULONG BytesPerCacheLine;
  ULONG BytesOffsetForCacheAlignment;
  ULONG BytesPerLogicalSector;
  ULONG BytesPerPhysicalSector;
  ULONG BytesOffsetForSectorAlignment;
} STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, *PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field <b>Version</b>

<dd>
<p>Contains the size of the structure STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR. The value of this member will change as members are added to the structure.</p>
</dd>

### -field <b>Size</b>

<dd>
<p>Specifies the total size of the descriptor, in bytes.</p>
</dd>

### -field <b>BytesPerCacheLine</b>

<dd>
<p>The number of bytes in a cache line of the device.</p>
</dd>

### -field <b>BytesOffsetForCacheAlignment</b>

<dd>
<p>The address offset necessary for proper cache access alignment, in bytes.</p>
</dd>

### -field <b>BytesPerLogicalSector</b>

<dd>
<p>The number of bytes in a logical sector of the device.</p>
</dd>

### -field <b>BytesPerPhysicalSector</b>

<dd>
<p>The number of bytes in a physical sector of the device.</p>
</dd>

### -field <b>BytesOffsetForSectorAlignment</b>

<dd>
<p>The logical sector offset within the first physical sector where the first logical sector is placed, in bytes.</p>
<p>Example:  Offset = 3 Logical sectors</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>+- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
|LBA      |X|X|X|0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|
|- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
|Physical |               |                  |
|Sector   |      0        |        1         |         2
+- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -</pre>
</td>
</tr>
</table></span></div>
<p>In this example, BytesOffsetForSectorAlignment = 3 * size_of_logical_sector.</p>
</dd>
</dl>

## -remarks
<p>Storage class drivers issue a device-control request with the I/O control code  <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve this structure, which contains access alignment information for data transfer operations. The structure can be retrieved either from the device object for the bus or from an FDO, which forwards the request to the underlying bus.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
