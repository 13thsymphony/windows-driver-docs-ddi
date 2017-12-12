---
UID: NS.NTDDMMC._FEATURE_DATA_DISC_CONTROL_BLOCKS
title: _FEATURE_DATA_DISC_CONTROL_BLOCKS
author: windows-driver-content
description: The FEATURE_DATA_DISC_CONTROL_BLOCKS structure holds an array of the data reported for the Disc Control Block feature.
old-location: storage\feature_data_disc_control_blocks.htm
old-project: storage
ms.assetid: ed39e714-38c5-45cf-b1f0-dd00b4d49895
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _FEATURE_DATA_DISC_CONTROL_BLOCKS, *PFEATURE_DATA_DISC_CONTROL_BLOCKS, FEATURE_DATA_DISC_CONTROL_BLOCKS
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
req.alt-api: FEATURE_DATA_DISC_CONTROL_BLOCKS
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
---

# _FEATURE_DATA_DISC_CONTROL_BLOCKS structure



## -description
The FEATURE_DATA_DISC_CONTROL_BLOCKS structure holds an array of the data reported for the Disc Control Block feature. 



## -syntax

````
typedef struct _FEATURE_DATA_DISC_CONTROL_BLOCKS {
  FEATURE_HEADER                      Header;
  FEATURE_DATA_DISC_CONTROL_BLOCKS_EX Data[];
} FEATURE_DATA_DISC_CONTROL_BLOCKS, *PFEATURE_DATA_DISC_CONTROL_BLOCKS;
````


## -struct-fields

### -field Header

Contains a <a href="storage.feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Data

Contains zero, one, or more disk control blocks. Each disk control block is contained in a <a href="storage.feature_data_disc_control_blocks_ex">FEATURE_DATA_DISC_CONTROL_BLOCKS_EX</a> structure. 


## -remarks
This structure holds data for the feature named "Disc Control Blocks" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can do reads and writes of disc control blocks. 


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
<a href="storage.feature_header">FEATURE_HEADER</a>
</dt>
<dt>
<a href="storage.feature_number">FEATURE_NUMBER</a>
</dt>
<dt>
<a href="storage.feature_data_disc_control_blocks_ex">FEATURE_DATA_DISC_CONTROL_BLOCKS_EX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DISC_CONTROL_BLOCKS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

