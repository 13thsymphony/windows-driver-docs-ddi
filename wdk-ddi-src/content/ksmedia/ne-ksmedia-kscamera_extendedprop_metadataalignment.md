---
UID: NE.ksmedia.KSCAMERA_EXTENDEDPROP_MetadataAlignment
title: KSCAMERA_EXTENDEDPROP_MetadataAlignment
author: windows-driver-content
description: This enumeration contains identifiers for the metadata alignment.
old-location: stream\kscamera_extendedprop_metadataalignment.htm
old-project: stream
ms.assetid: A122F923-D98E-4D73-896A-551A233E7491
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KSCAMERA_EXTENDEDPROP_MetadataAlignment, KSCAMERA_EXTENDEDPROP_MetadataAlignment
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_EXTENDEDPROP_MetadataAlignment
req.alt-loc: Ksmedia.h
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

# KSCAMERA_EXTENDEDPROP_MetadataAlignment enumeration



## -description
This enumeration contains identifiers for the metadata alignment.


## -syntax

````
typedef enum  { 
  KSCAMERA_EXTENDEDPROP_MetadataAlignment_16    = 4,
  KSCAMERA_EXTENDEDPROP_MetadataAlignment_32,
  KSCAMERA_EXTENDEDPROP_MetadataAlignment_64,
  KSCAMERA_EXTENDEDPROP_MetadataAlignment_128,
  KSCAMERA_EXTENDEDPROP_MetadataAlignment_256,
  KSCAMERA_EXTENDEDPROP_MetadataAlignment_512,
  KSCAMERA_EXTENDEDPROP_MetadataAlignment_1024,
  KSCAMERA_EXTENDEDPROP_MetadataAlignment_2048,
  KSCAMERA_EXTENDEDPROP_MetadataAlignment_4096,
  KSCAMERA_EXTENDEDPROP_MetadataAlignment_8192
} KSCAMERA_EXTENDEDPROP_MetadataAlignment;
````


## -enum-fields

### -field KSCAMERA_EXTENDEDPROP_MetadataAlignment_16

This identifies an alignment of 16 bytes.

### -field KSCAMERA_EXTENDEDPROP_MetadataAlignment_32

This identifies an alignment of 32 bytes.

### -field KSCAMERA_EXTENDEDPROP_MetadataAlignment_64

This identifies an alignment of 64 bytes.

### -field KSCAMERA_EXTENDEDPROP_MetadataAlignment_128

This identifies an alignment of 128 bytes.

### -field KSCAMERA_EXTENDEDPROP_MetadataAlignment_256

This identifies an alignment of 256 bytes.

### -field KSCAMERA_EXTENDEDPROP_MetadataAlignment_512

This identifies an alignment of 512 bytes.

### -field KSCAMERA_EXTENDEDPROP_MetadataAlignment_1024

This identifies an alignment of 1024 bytes.

### -field KSCAMERA_EXTENDEDPROP_MetadataAlignment_2048

This identifies an alignment of 2048 bytes.

### -field KSCAMERA_EXTENDEDPROP_MetadataAlignment_4096

This identifies an alignment of 4096 bytes.

### -field KSCAMERA_EXTENDEDPROP_MetadataAlignment_8192

This identifies an alignment of 8192 bytes.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>