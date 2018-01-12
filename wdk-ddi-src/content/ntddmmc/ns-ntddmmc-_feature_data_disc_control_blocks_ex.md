---
UID: NS:ntddmmc._FEATURE_DATA_DISC_CONTROL_BLOCKS_EX
title: _FEATURE_DATA_DISC_CONTROL_BLOCKS_EX
author: windows-driver-content
description: The FEATURE_DATA_DISC_CONTROL_BLOCKS_EX structure holds the data reported for a Disc Control Block.
old-location: storage\feature_data_disc_control_blocks_ex.htm
old-project: storage
ms.assetid: 08344cf3-7724-4c11-8855-ba061a0284f8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _FEATURE_DATA_DISC_CONTROL_BLOCKS_EX, FEATURE_DATA_DISC_CONTROL_BLOCKS_EX, *PFEATURE_DATA_DISC_CONTROL_BLOCKS_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FEATURE_DATA_DISC_CONTROL_BLOCKS_EX
req.alt-loc: ntddmmc.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: FEATURE_DATA_DISC_CONTROL_BLOCKS_EX, *PFEATURE_DATA_DISC_CONTROL_BLOCKS_EX
---

# _FEATURE_DATA_DISC_CONTROL_BLOCKS_EX structure



## -description
The FEATURE_DATA_DISC_CONTROL_BLOCKS_EX structure holds the data reported for a Disc Control Block. 



## -syntax

````
typedef struct _FEATURE_DATA_DISC_CONTROL_BLOCKS_EX {
  UCHAR ContentDescriptor[4];
} FEATURE_DATA_DISC_CONTROL_BLOCKS_EX, *PFEATURE_DATA_DISC_CONTROL_BLOCKS_EX;
````


## -struct-fields

### -field ContentDescriptor

Contains the first of one or more control blocks. The bytes in this array are arranged in big-endian order. <b>ContentDescriptor</b>[0] contains the most significant byte, and <b>ContentDescriptor</b>[3] contains the least significant byte.


## -remarks
This structure holds data for the feature named "Disc Control Blocks" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can read or write Disc Control Blocks.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddmmc.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddmmc\ns-ntddmmc-_feature_data_disc_control_blocks.md">FEATURE_DATA_DISC_CONTROL_BLOCKS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DISC_CONTROL_BLOCKS_EX structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

