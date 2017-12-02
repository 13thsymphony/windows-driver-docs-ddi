---
UID: NS.ntdddisk._REASSIGN_BLOCKS
title: REASSIGN_BLOCKS
author: windows-driver-content
description: The REASSIGN_BLOCKS structure is used in conjunction with the IOCTL_DISK_REASSIGN_BLOCKS request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.
old-location: storage\reassign_blocks.htm
old-project: storage
ms.assetid: b79f15d8-b777-43dc-82b9-fcd1ba19aebd
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: REASSIGN_BLOCKS, REASSIGN_BLOCKS, *PREASSIGN_BLOCKS
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
req.alt-api: REASSIGN_BLOCKS
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

# REASSIGN_BLOCKS structure



## -description
<p>The <b>REASSIGN_BLOCKS</b> structure is used in conjunction with the <a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-reassign-blocks.md">IOCTL_DISK_REASSIGN_BLOCKS</a> request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.</p>


## -syntax

````
typedef struct _REASSIGN_BLOCKS {
  USHORT Reserved;
  USHORT Count;
  ULONG  BlockNumber[1];
} REASSIGN_BLOCKS, *PREASSIGN_BLOCKS;
````


## -struct-fields
<dl>

### -field Reserved

<dd>
<p>Reserved for system use. </p>
</dd>

### -field Count

<dd>
<p>Contains the number of blocks in the array pointed to by <b>BlockNumber</b> to reassign. </p>
</dd>

### -field BlockNumber

<dd>
<p>Contains an array of block numbers corresponding to damaged blocks. These numbers will be reassigned to good blocks taken from the device's spare block pool. </p>
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
<a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-reassign-blocks.md">IOCTL_DISK_REASSIGN_BLOCKS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20REASSIGN_BLOCKS structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
