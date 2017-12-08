---
UID: NE.iscsidef.PISCSI_DIGEST_TYPES
title: PISCSI_DIGEST_TYPES
author: windows-driver-content
description: The ISCSI_DIGEST_TYPES enumeration indicates the digest type.
old-location: storage\iscsi_digest_types.htm
old-project: storage
ms.assetid: 0515dd76-ef1f-4f0f-a7d7-1b3b07e0523d
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PISCSI_DIGEST_TYPES, ISCSI_DIGEST_TYPES, *PISCSI_DIGEST_TYPES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iscsidef.h
req.include-header: Iscsidef.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISCSI_DIGEST_TYPES
req.alt-loc: iscsidef.h
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

# PISCSI_DIGEST_TYPES enumeration



## -description
The ISCSI_DIGEST_TYPES enumeration indicates the digest type.


## -syntax

````
typedef enum  { 
  ISCSI_DIGEST_TYPE_NONE    = 0,
  ISCSI_DIGEST_TYPE_CRC32C  = 1
} ISCSI_DIGEST_TYPES, *PISCSI_DIGEST_TYPES;
````


## -enum-fields

### -field ISCSI_DIGEST_TYPE_NONE

There is no usable digest that guarantees data integrity. 

### -field ISCSI_DIGEST_TYPE_CRC32C

The digest that guarantees data integrity uses a 32-bit cyclic redundancy check. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Iscsidef.h (include Iscsidef.h)</dt>
</dl>
</td>
</tr>
</table>