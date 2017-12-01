---
UID: NS.ntddtape._TAPE_SET_POSITION
title: TAPE_SET_POSITION
author: windows-driver-content
description: The TAPE_SET_POSITION structure is used in conjunction with the IOCTL_TAPE_SET_POSITION request to move the current position on the tape to the specified partition and offset.
old-location: storage\tape_set_position.htm
old-project: storage
ms.assetid: c9f462b2-4b56-4138-a374-9e9d3e1ae295
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: TAPE_SET_POSITION, TAPE_SET_POSITION, *PTAPE_SET_POSITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddtape.h
req.include-header: Ntddtape.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TAPE_SET_POSITION
req.alt-loc: ntddtape.h
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

# TAPE_SET_POSITION structure



## -description
<p>The TAPE_SET_POSITION structure is used in conjunction with the <a href="..\ntddtape\ni-ntddtape-ioctl-tape-set-position.md">IOCTL_TAPE_SET_POSITION</a> request to move the current position on the tape to the specified partition and offset.</p>


## -syntax

````
typedef struct _TAPE_SET_POSITION {
  ULONG         Method;
  ULONG         Partition;
  LARGE_INTEGER Offset;
  BOOLEAN       Immediate;
} TAPE_SET_POSITION, *PTAPE_SET_POSITION;
````


## -struct-fields
<dl>

### -field <b>Method</b>

<dd>
<p>Indicates the type of positioning to perform. This member must have one of the following values:</p>
<p></p>
<dl>

### -field <a id="TAPE_REWIND"></a><a id="tape_rewind"></a>TAPE_REWIND

<dd>
<p>Positions the tape at the beginning of the partition indicated in <b>Partition</b> if the media is partitioned, and to the beginning of the media if the media is not partitioned. If the media is not partitioned, <b>Partition</b> must be set to zero. The <b>Offset</b> member is ignored. </p>
</dd>

### -field <a id="TAPE_ABSOLUTE_BLOCK"></a><a id="tape_absolute_block"></a>TAPE_ABSOLUTE_BLOCK

<dd>
<p>Positions the tape at the absolute block address located at the offset from the beginning specified by <b>Offset</b>. The value in the <b>Partition</b> member is ignored. </p>
</dd>

### -field <a id="TAPE_LOGICAL_BLOCK"></a><a id="tape_logical_block"></a>TAPE_LOGICAL_BLOCK

<dd>
<p>Positions the tape to the logical block address specified by <b>Offset</b>, relative to the beginning of the partition indicated in <b>Partition</b>. If the media is not partitioned, <b>Partition</b> must be set to zero. </p>
</dd>

### -field <a id="TAPE_PSEUDO_LOGICAL_BLOCK"></a><a id="tape_pseudo_logical_block"></a>TAPE_PSEUDO_LOGICAL_BLOCK

<dd>
<p>Positions the tape to the pseudological block address specified by <b>Offset</b>, relative to the beginning of the partition indicated in <b>Partition</b>. If the media is not partitioned, <b>Partition</b> must be to zero.</p>
</dd>

### -field <a id="TAPE_SPACE_END_OF_DATA"></a><a id="tape_space_end_of_data"></a>TAPE_SPACE_END_OF_DATA

<dd>
<p>Positions the tape at the end of the partition indicated in <b>Partition</b>, or if the media is not partitioned, at the end of the tape. The <b>Offset</b> member is ignored. </p>
</dd>

### -field <a id="TAPE_SPACE_RELATIVE_BLOCKS"></a><a id="tape_space_relative_blocks"></a>TAPE_SPACE_RELATIVE_BLOCKS

<dd>
<p>Starting from the current position, positions the tape immediately after the number of blocks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. </p>
</dd>

### -field <a id="TAPE_SPACE_FILEMARKS"></a><a id="tape_space_filemarks"></a>TAPE_SPACE_FILEMARKS

<dd>
<p>Starting from the current position, positions the tape immediately after the number of filemarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. </p>
</dd>

### -field <a id="TAPE_SPACE_SEQUENTIAL_FMKS"></a><a id="tape_space_sequential_fmks"></a>TAPE_SPACE_SEQUENTIAL_FMKS

<dd>
<p>Starting from the current position, positions the tape immediately after the next occurrence, if any, of the number of consecutive filemarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. </p>
</dd>

### -field <a id="TAPE_SPACE_SETMARKS"></a><a id="tape_space_setmarks"></a>TAPE_SPACE_SETMARKS

<dd>
<p>Starting from the current position, positions the tape immediately after the number of setmarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. </p>
</dd>

### -field <a id="TAPE_SPACE_SEQUENTIAL_SMKS"></a><a id="tape_space_sequential_smks"></a>TAPE_SPACE_SEQUENTIAL_SMKS

<dd>
<p>Starting from the current position, positions the tape immediately after the next occurrence, if any, of the number of consecutive setmarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. </p>
</dd>
</dl>
</dd>

### -field <b>Partition</b>

<dd>
<p>Indicates the partition in which to set the tape's position. This member must have one of the following values:</p>
<p>
<dl>

### -field NOT_PARTITIONED (or zero)


### -field DATA_PARTITION


### -field DIRECTORY_PARTITION

</dl>
</p>
<p>If the media is not partitioned, this member is zero. </p>
</dd>

### -field <b>Offset</b>

<dd>
<p>Specifies an offset whose type depends on the value in <b>Method</b>. If the specified method positions the tape to a block address, <b>Offset</b> specifies the byte offset into the specified partition. If the specified method is to skip blocks, filemarks, or setmarks, <b>Offset</b> specifies the number to skip. If <b>Offset</b> is zero, the tape is positioned at the beginning of the partition. </p>
</dd>

### -field <b>Immediate</b>

<dd>
<p>When set to <b>TRUE</b>, indicates that the target device should return status immediately. When set to <b>FALSE</b>, indicates that the device should return status after the operation is complete. </p>
</dd>
</dl>

## -remarks
<p>Note that a drive or a tape may not support all <b>Method</b> values.</p>

<p>Partitions are numbered logically from 1 to N. However, a partition number does not imply a physical position on the tape. For example, partition number one might not be at the beginning of the media.</p>

<p>When the offset specifies a number of blocks, filemarks, or setmarks to position over, a positive value N in the offset causes forward positioning over N blocks, filemarks, or setmarks, halting on the end-of-partition or end-of-tape side of the block, filemark, or setmark. A zero value in the offset causes no change of position. A negative value N in the offset causes reverse positioning, toward the beginning of the partition or the tape media, over N blocks, filemarks, or setmarks, halting on the beginning-of-partition side of a block, filemark, or setmark.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddtape.h (include Ntddtape.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddtape\ni-ntddtape-ioctl-tape-set-position.md">IOCTL_TAPE_SET_POSITION</a>
</dt>
<dt>
<a href="storage.tapeminisetposition">TapeMiniSetPosition</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_SET_POSITION structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
