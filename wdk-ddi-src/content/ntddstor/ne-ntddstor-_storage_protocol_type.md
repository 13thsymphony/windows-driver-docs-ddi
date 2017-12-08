---
UID: NE.ntddstor._STORAGE_PROTOCOL_TYPE
title: _STORAGE_PROTOCOL_TYPE
author: windows-driver-content
description: This enumeration is used to define the different storage command protocols that are used between software and hardware.
old-location: storage\storage_protocol_type.htm
old-project: storage
ms.assetid: 3CC4DF0A-26F1-4825-AD89-D56B0D5F4AC6
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _STORAGE_PROTOCOL_TYPE, *PSTORAGE_PROTOCOL_TYPE, STORAGE_PROTOCOL_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_PROTOCOL_TYPE
req.alt-loc: Ntddstor.h
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

# _STORAGE_PROTOCOL_TYPE enumeration



## -description
This enumeration is used to define the different storage command protocols that are used between software and hardware.


## -syntax

````
typedef enum _STORAGE_PROTOCOL_TYPE { 
  ProtocolTypeUnknown      = 0,   // 0x0
  ProtocolTypeScsi,
  ProtocolTypeAta,
  ProtocolTypeNvme,
  ProtocolTypeSd,
  ProtocolTypeUfs,
  ProtocolTypeProprietary  = 126, // 0x7E
  ProtocolTypeMaxReserved  = 127 // 0x7F
} STORAGE_PROTOCOL_TYPE;
````


## -enum-fields

### -field ProtocolTypeUnknown

Unknown protocol type.

### -field ProtocolTypeScsi

SCSI protocol type.

### -field ProtocolTypeAta

ATA protocol type.

### -field ProtocolTypeNvme

NVMe protocol type.

### -field ProtocolTypeSd

SD protocol type.

### -field ProtocolTypeUfs

UFS protocol type.

### -field ProtocolTypeProprietary

 Vendor-specific protocol type.

### -field ProtocolTypeMaxReserved

Reserved.

## -remarks
Protocol types that are 128 (0x80) and above in value are reserved for Microsoft use.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>