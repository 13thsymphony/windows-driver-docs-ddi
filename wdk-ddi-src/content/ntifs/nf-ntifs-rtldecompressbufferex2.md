---
UID: NF.ntifs.RtlDecompressBufferEx2
title: RtlDecompressBufferEx2 function
author: windows-driver-content
description: The RtlDecompressBufferEx2 function decompresses an entire compressed buffer, using multiple processors where possible. Multiple processor support is only implemented for kernel mode callers.
old-location: ifsk\rtldecompressbufferex2.htm
old-project: ifsk
ms.assetid: 8AE36F8C-F7FA-4291-A244-3664CCBB8073
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlDecompressBufferEx2
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
req.alt-api: RtlDecompressBufferEx2
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
---

# RtlDecompressBufferEx2 function



## -description
The <b>RtlDecompressBufferEx2</b> function decompresses an entire compressed buffer, using multiple processors where possible. Multiple processor support is only implemented for kernel mode callers.


## -syntax

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


## -parameters

### -param CompressionFormat [in]

A bitmask that specifies the compression format of the compressed buffer. This parameter must be set to COMPRESSION_FORMAT_LZNT1. The meaning of this and other related compression format values are as follows.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param COMPRESSION_FORMAT_NONE

</td>
<td width="60%">
Not supported by this function.
</td>
</tr>
<tr>

### -param COMPRESSION_FORMAT_DEFAULT

</td>
<td width="60%">
Not supported by this function.
</td>
</tr>
<tr>

### -param COMPRESSION_FORMAT_LZNT1

</td>
<td width="60%">
The function will perform LZ decompression.
</td>
</tr>
<tr>

### -param COMPRESSION_FORMAT_XPRESS

</td>
<td width="60%">
The function will perform Xpress decompression.
</td>
</tr>
<tr>

### -param COMPRESSION_FORMAT_XPRESS_HUFF

</td>
<td width="60%">
The function will perform Xpress Huffman decompression.
</td>
</tr>
</table>
 

### -param UncompressedBuffer [out]

A pointer to a caller-allocated buffer (allocated from a  paged or non-paged pool) that receives the decompressed data from <i>CompressedBuffer</i>. This parameter is required and cannot be <b>NULL</b>.

### -param UncompressedBufferSize [in]

The size, in bytes, of the <i>UncompressedBuffer</i> buffer.

### -param CompressedBuffer [in]

A pointer to the buffer that contains the data to decompress. This parameter is required and cannot be <b>NULL</b>.

### -param CompressedBufferSize [in]

The size, in bytes, of the <i>CompressedBuffer</i> buffer.

### -param UncompressedChunkSize [in]

The size, in bytes, of each chunk within the compression buffer.  Valid values are 512, 1024, 2048 and 4096.

### -param FinalUncompressedSize [out]

A pointer to a caller-allocated variable that receives the size, in bytes, of the decompressed data stored in <i>UncompressedBuffer</i>. This parameter is required and cannot be <b>NULL</b>.

### -param WorkSpace [in, optional]

A pointer to a caller-allocated work space buffer used by the <b>RtlDecompressBufferEx2</b> function during decompression. Use the <a href="ifsk.rtlgetcompressionworkspacesize">RtlGetCompressionWorkSpaceSize</a> function to determine the correct work space buffer size.

## -returns
<b>RtlDecompressBufferEx2</b> returns an appropriate error status value, such as one of the following.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The <i>CompressedBuffer</i> buffer was successfully decompressed.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid compression format was specified through the <i>CompressionFormat</i> parameter. If <i>CompressionFormat</i> is either COMPRESSION_FORMAT_NONE or COMPRESSION_FORMAT_DEFAULT (but not both), this value is returned.
<dl>
<dt><b>STATUS_UNSUPPORTED_COMPRESSION</b></dt>
</dl>An invalid compression format was specified through the <i>CompressionFormat</i> parameter. If <i>CompressionFormat</i> is not one of the following, STATUS_UNSUPPORTED_COMPRESSION is returned:

 COMPRESSION_FORMAT_LZNT1

 COMPRESSION_FORMAT_XPRESS

 COMPRESSION_FORMAT_XPRESS_HUFF

 COMPRESSION_FORMAT_NONE

 COMPRESSION_FORMAT_DEFAULT
<dl>
<dt><b>STATUS_BAD_COMPRESSION_BUFFER</b></dt>
</dl><i>UncompressedBuffer</i> is not large enough to contain the uncompressed data.

 

## -remarks
The <b>RtlDecompressBufferEx2</b> function takes as input an entire compressed buffer and produces its decompressed equivalent provided that the uncompressed data fits within the specified destination buffer.

To decompress only a portion of a compressed buffer (that is, a "fragment" of the buffer), use the <a href="ifsk.rtldecompressfragment">RtlDecompressFragment</a> function.

To compress an uncompressed buffer, use the <a href="ifsk.rtlcompressbuffer">RtlCompressBuffer</a> function.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in starting in Windows 10.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Fltkernel.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= APC_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.file_compression_information">FILE_COMPRESSION_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.rtldecompressbuffer">RtlDecompressBuffer</a>
</dt>
<dt>
<a href="ifsk.rtldecompressbufferex">RtlDecompressBufferEx</a>
</dt>
<dt>
<a href="ifsk.rtldecompressfragment">RtlDecompressFragment</a>
</dt>
<dt>
<a href="ifsk.rtldecompressfragmentex">RtlDecompressFragmentEx</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlDecompressBufferEx2 function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
