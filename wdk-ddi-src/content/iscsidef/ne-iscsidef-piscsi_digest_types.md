---
UID : NE:iscsidef.PISCSI_DIGEST_TYPES
title : "*PISCSI_DIGEST_TYPES"
author : windows-driver-content
description : The ISCSI_DIGEST_TYPES enumeration indicates the digest type.
old-location : storage\iscsi_digest_types.htm
old-project : storage
ms.assetid : 0515dd76-ef1f-4f0f-a7d7-1b3b07e0523d
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : iscsidef/ISCSI_DIGEST_TYPES, iscsidef/PISCSI_DIGEST_TYPES, ISCSI_DIGEST_TYPES enumeration [Storage Devices], PISCSI_DIGEST_TYPES, iscsidef/ISCSI_DIGEST_TYPE_NONE, ISCSI_DIGEST_TYPES, iscsidef/ISCSI_DIGEST_TYPE_CRC32C, ISCSI_DIGEST_TYPE_CRC32C, PISCSI_DIGEST_TYPES enumeration pointer [Storage Devices], structs-iSCSI_107b48fe-7dd1-41d3-b329-d82ba0cd13d4.xml, storage.iscsi_digest_types, ISCSI_DIGEST_TYPE_NONE, *PISCSI_DIGEST_TYPES
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : iscsidef.h
req.include-header : Iscsidef.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PISCSI_DIGEST_TYPES, ISCSI_DIGEST_TYPES"
---

# *PISCSI_DIGEST_TYPES Enumeration
The ISCSI_DIGEST_TYPES enumeration indicates the digest type.

## Syntax
````
typedef enum  { 
  ISCSI_DIGEST_TYPE_NONE    = 0,
  ISCSI_DIGEST_TYPE_CRC32C  = 1
} ISCSI_DIGEST_TYPES, *PISCSI_DIGEST_TYPES;
````

## Constants

<table>

<tr>
<td>ISCSI_DIGEST_TYPE_CRC32C</td>
<td>The digest that guarantees data integrity uses a 32-bit cyclic redundancy check.</td>
</tr>

<tr>
<td>ISCSI_DIGEST_TYPE_NONE</td>
<td>There is no usable digest that guarantees data integrity.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iscsidef.h (include Iscsidef.h) |