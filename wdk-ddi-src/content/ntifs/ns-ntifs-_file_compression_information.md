---
UID: NS.NTIFS._FILE_COMPRESSION_INFORMATION
title: _FILE_COMPRESSION_INFORMATION
author: windows-driver-content
description: The FILE_COMPRESSION_INFORMATION structure describes the state of a compressed data buffer.
old-location: ifsk\file_compression_information.htm
old-project: ifsk
ms.assetid: 69a360d9-6e17-4979-a4f3-219ac0739d99
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _FILE_COMPRESSION_INFORMATION, FILE_COMPRESSION_INFORMATION, *PFILE_COMPRESSION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_COMPRESSION_INFORMATION
req.alt-loc: ntifs.h
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

# _FILE_COMPRESSION_INFORMATION structure



## -description
The FILE_COMPRESSION_INFORMATION structure describes the state of a compressed data buffer.


## -syntax

````
typedef struct _FILE_COMPRESSION_INFORMATION {
  LARGE_INTEGER CompressedFileSize;
  USHORT        CompressionFormat;
  UCHAR         CompressionUnitShift;
  UCHAR         ChunkShift;
  UCHAR         ClusterShift;
  UCHAR         Reserved[3];
} FILE_COMPRESSION_INFORMATION, *PFILE_COMPRESSION_INFORMATION;
````


## -struct-fields

### -field CompressedFileSize

The size, in bytes, of the compressed file.

### -field CompressionFormat

The compression format. This member must have one of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
COMPRESSION_FORMAT_NONE
</td>
<td>
No compression format.
</td>
</tr>
<tr>
<td>
COMPRESSION_FORMAT_DEFAULT
</td>
<td>
Default compression format.
</td>
</tr>
<tr>
<td>
COMPRESSION_FORMAT_LZNT1
</td>
<td>
LZNT1 compression format.
</td>
</tr>
</table>
 

### -field CompressionUnitShift

The log, base 2, of the number of clusters per compression
unit. In the NTFS file system, this value is NTFS_CLUSTERS_PER_COMPRESSION.

### -field ChunkShift

The log, base 2, of the number of bytes in a chunk. In other words, the size in bytes of the chunk is 2 ** <b>ChunkShift</b>, or (1 &lt;&lt; <b>ChunkShift</b>). 

### -field ClusterShift

The log, base 2, of the minimum number of clusters by which compression must reduce the size of the compression unit. If compression does not reduce the size of the compression unit by at least 2 ** <b>ClusterShift</b> clusters (or 1 &lt;&lt; <b>ClusterShift</b> clusters), compression will not occur. Each compression unit must occupy at least one cluster less than the uncompressed data would occupy.

### -field Reserved

Reserved

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.flt_parameters_for_irp_mj_query_information">FLT_PARAMETERS for IRP_MJ_QUERY_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.fltqueryinformationfile">FltQueryInformationFile</a>
</dt>
<dt>
<a href="ifsk.irp_mj_query_information">IRP_MJ_QUERY_INFORMATION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_COMPRESSION_INFORMATION structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
