---
UID: NS.SCSI.PBLOCK_DEVICE_RANGE_DESCRIPTOR
title: PBLOCK_DEVICE_RANGE_DESCRIPTOR
author: windows-driver-content
description: The BLOCK_DEVICE_RANGE_DESCRIPTOR structure describes a range of logical blocks associated with various fragments of a file for an offload copy operation.
old-location: storage\block_device_range_descriptor.htm
old-project: storage
ms.assetid: 6B262D38-8BD6-43B5-96AB-6D311B8EBA88
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PBLOCK_DEVICE_RANGE_DESCRIPTOR, BLOCK_DEVICE_RANGE_DESCRIPTOR, *PBLOCK_DEVICE_RANGE_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
req.include-header: Scsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BLOCK_DEVICE_RANGE_DESCRIPTOR
req.alt-loc: scsi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# PBLOCK_DEVICE_RANGE_DESCRIPTOR structure



## -description
The <b>BLOCK_DEVICE_RANGE_DESCRIPTOR</b> structure describes a range of logical blocks associated with various fragments of a file for an offload copy operation.


## -syntax

````
typedef struct _BLOCK_DEVICE_RANGE_DESCRIPTOR {
  UCHAR LogicalBlockAddress[8];
  UCHAR TransferLength[4];
  UCHAR Reserved[4];
} BLOCK_DEVICE_RANGE_DESCRIPTOR, *PBLOCK_DEVICE_RANGE_DESCRIPTOR;
````


## -struct-fields

### -field LogicalBlockAddress

The starting logical block address of a block range.

### -field TransferLength

The length, in logical blocks, of the block range.

### -field Reserved

Reserved bytes.

## -remarks
If <i>TransferLength</i> is set to 0, the range descriptor is considered valid and does not cause an error when included in a token parameter list. No operation will be performed for this descriptor.

All multibyte values are in big endian format. Prior to setting, these values must be converted from the endian format of the current platform.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows 8.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Scsi.h (include Scsi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.populate_token_header">POPULATE_TOKEN_HEADER</a>
</dt>
<dt>
<a href="storage.write_using_token_header">WRITE_USING_TOKEN_HEADER</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20BLOCK_DEVICE_RANGE_DESCRIPTOR structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
