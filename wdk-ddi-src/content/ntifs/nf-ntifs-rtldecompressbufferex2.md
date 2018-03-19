---
UID: NF:ntifs.RtlDecompressBufferEx2
title: RtlDecompressBufferEx2 function
author: windows-driver-content
description: The RtlDecompressBufferEx2 function decompresses an entire compressed buffer, using multiple processors where possible. Multiple processor support is only implemented for kernel mode callers.
old-location: ifsk\rtldecompressbufferex2.htm
old-project: ifsk
ms.assetid: 8AE36F8C-F7FA-4291-A244-3664CCBB8073
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: COMPRESSION_FORMAT_DEFAULT, COMPRESSION_FORMAT_LZNT1, COMPRESSION_FORMAT_NONE, COMPRESSION_FORMAT_XPRESS, COMPRESSION_FORMAT_XPRESS_HUFF, RtlDecompressBufferEx2, RtlDecompressBufferEx2 function [Installable File System Drivers], ifsk.rtldecompressbufferex2, ntifs/RtlDecompressBufferEx2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting in Windows 10.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlDecompressBufferEx2
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlDecompressBufferEx2 function
The <b>RtlDecompressBufferEx2</b> function decompresses an entire compressed buffer, using multiple processors where possible. Multiple processor support is only implemented for kernel mode callers.

## Syntax

````
NTSTATUS RtlDecompressBufferEx2(
  _In_     USHORT CompressionFormat,
  _Out_    PUCHAR UncompressedBuffer,
  _In_     ULONG  UncompressedBufferSize,
  _In_     PUCHAR CompressedBuffer,
  _In_     ULONG  CompressedBufferSize,
  _In_     ULONG  UncompressedChunkSize,
  _Out_    PULONG FinalUncompressedSize,
  _In_opt_ PVOID  WorkSpace
);
````

## Parameters

`CompressionFormat`

A bitmask that specifies the compression format of the compressed buffer. This parameter must be set to COMPRESSION_FORMAT_LZNT1. The meaning of this and other related compression format values are as follows.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_NONE"></a><a id="compression_format_none"></a><dl>
<dt><b>COMPRESSION_FORMAT_NONE</b></dt>
</dl>
</td>
<td width="60%">
Not supported by this function.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_DEFAULT"></a><a id="compression_format_default"></a><dl>
<dt><b>COMPRESSION_FORMAT_DEFAULT</b></dt>
</dl>
</td>
<td width="60%">
Not supported by this function.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_LZNT1"></a><a id="compression_format_lznt1"></a><dl>
<dt><b>COMPRESSION_FORMAT_LZNT1</b></dt>
</dl>
</td>
<td width="60%">
The function will perform LZ decompression.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_XPRESS"></a><a id="compression_format_xpress"></a><dl>
<dt><b>COMPRESSION_FORMAT_XPRESS</b></dt>
</dl>
</td>
<td width="60%">
The function will perform Xpress decompression.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_XPRESS_HUFF"></a><a id="compression_format_xpress_huff"></a><dl>
<dt><b>COMPRESSION_FORMAT_XPRESS_HUFF</b></dt>
</dl>
</td>
<td width="60%">
The function will perform Xpress Huffman decompression.

</td>
</tr>
</table>

`UncompressedBuffer`

A pointer to a caller-allocated buffer (allocated from a  paged or non-paged pool) that receives the decompressed data from <i>CompressedBuffer</i>. This parameter is required and cannot be <b>NULL</b>.

`UncompressedBufferSize`

The size, in bytes, of the <i>UncompressedBuffer</i> buffer.

`CompressedBuffer`

A pointer to the buffer that contains the data to decompress. This parameter is required and cannot be <b>NULL</b>.

`CompressedBufferSize`

The size, in bytes, of the <i>CompressedBuffer</i> buffer.

`UncompressedChunkSize`

The size, in bytes, of each chunk within the compression buffer.  Valid values are 512, 1024, 2048 and 4096.

`FinalUncompressedSize`

A pointer to a caller-allocated variable that receives the size, in bytes, of the decompressed data stored in <i>UncompressedBuffer</i>. This parameter is required and cannot be <b>NULL</b>.

`WorkSpace`

A pointer to a caller-allocated work space buffer used by the <b>RtlDecompressBufferEx2</b> function during decompression. Use the <a href="..\ntifs\nf-ntifs-rtlgetcompressionworkspacesize.md">RtlGetCompressionWorkSpaceSize</a> function to determine the correct work space buffer size.


## Return Value

<b>RtlDecompressBufferEx2</b> returns an appropriate error status value, such as one of the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The <i>CompressedBuffer</i> buffer was successfully decompressed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid compression format was specified through the <i>CompressionFormat</i> parameter. If <i>CompressionFormat</i> is either COMPRESSION_FORMAT_NONE or COMPRESSION_FORMAT_DEFAULT (but not both), this value is returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUPPORTED_COMPRESSION</b></dt>
</dl>
</td>
<td width="60%">
An invalid compression format was specified through the <i>CompressionFormat</i> parameter. If <i>CompressionFormat</i> is not one of the following, STATUS_UNSUPPORTED_COMPRESSION is returned:

<ul>
<li>
 COMPRESSION_FORMAT_LZNT1

</li>
<li>
 COMPRESSION_FORMAT_XPRESS

</li>
<li>
 COMPRESSION_FORMAT_XPRESS_HUFF

</li>
<li>
 COMPRESSION_FORMAT_NONE

</li>
<li>
 COMPRESSION_FORMAT_DEFAULT

</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BAD_COMPRESSION_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
<i>UncompressedBuffer</i> is not large enough to contain the uncompressed data.

</td>
</tr>
</table>

## Remarks

The <b>RtlDecompressBufferEx2</b> function takes as input an entire compressed buffer and produces its decompressed equivalent provided that the uncompressed data fits within the specified destination buffer.

To decompress only a portion of a compressed buffer (that is, a "fragment" of the buffer), use the <a href="..\ntifs\nf-ntifs-rtldecompressfragment.md">RtlDecompressFragment</a> function.

To compress an uncompressed buffer, use the <a href="..\ntifs\nf-ntifs-rtlcompressbuffer.md">RtlCompressBuffer</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in starting in Windows 10.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Fltkernel.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-rtldecompressfragmentex.md">RtlDecompressFragmentEx</a>



<a href="..\ntifs\ns-ntifs-_file_compression_information.md">FILE_COMPRESSION_INFORMATION</a>



<a href="..\ntifs\nf-ntifs-rtldecompressbuffer.md">RtlDecompressBuffer</a>



<a href="..\ntifs\nf-ntifs-rtldecompressfragment.md">RtlDecompressFragment</a>



<a href="..\ntifs\nf-ntifs-rtldecompressbufferex.md">RtlDecompressBufferEx</a>