---
UID: NS:ntifs._FILE_COMPRESSION_INFORMATION
title: "_FILE_COMPRESSION_INFORMATION"
author: windows-driver-content
description: The FILE_COMPRESSION_INFORMATION structure describes the state of a compressed data buffer.
old-location: ifsk\file_compression_information.htm
old-project: ifsk
ms.assetid: 69a360d9-6e17-4979-a4f3-219ac0739d99
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_COMPRESSION_INFORMATION, FILE_COMPRESSION_INFORMATION, FILE_COMPRESSION_INFORMATION structure [Installable File System Drivers], PFILE_COMPRESSION_INFORMATION, PFILE_COMPRESSION_INFORMATION structure pointer [Installable File System Drivers], _FILE_COMPRESSION_INFORMATION, fileinformationstructures_76adaca7-2c3e-4c87-8715-da468416e95a.xml, ifsk.file_compression_information, ntifs/FILE_COMPRESSION_INFORMATION, ntifs/PFILE_COMPRESSION_INFORMATION"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FILE_COMPRESSION_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_COMPRESSION_INFORMATION, *PFILE_COMPRESSION_INFORMATION
---

# _FILE_COMPRESSION_INFORMATION structure
The FILE_COMPRESSION_INFORMATION structure describes the state of a compressed data buffer.

## Syntax
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

## Members


`CompressedFileSize`

The size, in bytes, of the compressed file.

`CompressionFormat`

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

`CompressionUnitShift`

The log, base 2, of the number of clusters per compression

unit. In the NTFS file system, this value is NTFS_CLUSTERS_PER_COMPRESSION.

`ChunkShift`

The log, base 2, of the number of bytes in a chunk. In other words, the size in bytes of the chunk is 2 ** <b>ChunkShift</b>, or (1 &lt;&lt; <b>ChunkShift</b>).

`ClusterShift`

The log, base 2, of the minimum number of clusters by which compression must reduce the size of the compression unit. If compression does not reduce the size of the compression unit by at least 2 ** <b>ClusterShift</b> clusters (or 1 &lt;&lt; <b>ClusterShift</b> clusters), compression will not occur. Each compression unit must occupy at least one cluster less than the uncompressed data would occupy.

`Reserved`

Reserved


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549283">IRP_MJ_QUERY_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryinformationfile.md">FltQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544756">FLT_PARAMETERS for IRP_MJ_QUERY_INFORMATION</a>