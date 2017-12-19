---
UID: NS.WDM._CLS_IO_STATISTICS_HEADER
title: _CLS_IO_STATISTICS_HEADER
author: windows-driver-content
description: The CLFS_IO_STATISTICS_HEADER structure holds the header portion of a CLFS_IO_STATISTICS structure.
old-location: kernel\clfs_io_statistics_header.htm
old-project: kernel
ms.assetid: ac0da755-ea2f-4b68-947c-c314d114f273
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _CLS_IO_STATISTICS_HEADER, *PCLS_IO_STATISTICS_HEADER, PPCLS_IO_STATISTICS_HEADER, PCLS_IO_STATISTICS_HEADER, CLS_IO_STATISTICS_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CLS_IO_STATISTICS_HEADER
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _CLS_IO_STATISTICS_HEADER structure



## -description
The <b>CLFS_IO_STATISTICS_HEADER</b> structure holds the header portion of a <a href="kernel.clfs_io_statistics">CLFS_IO_STATISTICS</a> structure.



## -syntax

````
typedef struct _CLS_IO_STATISTICS_HEADER {
  UCHAR              ubMajorVersion;
  UCHAR              ubMinorVersion;
  CLFS_IOSTATS_CLASS eStatsClass;
  USHORT             cbLength;
  ULONG              coffData;
} CLS_IO_STATISTICS_HEADER, *PCLS_IO_STATISTICS_HEADER, **PPCLS_IO_STATISTICS_HEADER, CLFS_IO_STATISTICS_HEADER, *PCLFS_IO_STATISTICS_HEADER, **PPCLFS_IO_STATISTICS_HEADER;
````


## -struct-fields

### -field ubMajorVersion

The major version of the <a href="kernel.clfs_io_statistics">CLFS_IO_STATISTICS</a> structure.


### -field ubMinorVersion

The minor version of the <b>CLFS_IO_STATISTICS</b> structure.


### -field eStatsClass

Reserved for future use. This member is ignored. 


### -field cbLength

The size, in bytes, of the <b>CLFS_IO_STATISTICS</b> structure, including the header.


### -field coffData

The offset, in bytes, from the beginning of the <b>CLFS_IO_STATISTICS</b> structure to the beginning of the statistics data. This member allows for transparent modifications to the header. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.clfsgetiostatistics">ClfsGetIoStatistics</a>
</dt>
<dt>
<a href="kernel.clfs_io_statistics">CLFS_IO_STATISTICS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLS_IO_STATISTICS_HEADER structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

